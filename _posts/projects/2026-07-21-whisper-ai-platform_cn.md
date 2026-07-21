---
layout: post
title: "Whisper AI 平台 —— Azure 上的自助式 AI 转写平台"
author: Zhien Li
category: projects
lang: cn
ref: whisper-ai-platform
tags:
  - content: 云平台
  - content: AI/ML
  - content: DevOps
preview: projectImg/whisper-ai-platform.svg
align: align-left
urlLinks:
  - url: https://github.com/li6834300/learn_platform_whisper
    name: GitHub 仓库
---

我在 Azure 上搭了一个**自助式 AI 转写平台**。目的不是做一个转写产品，而是把 AI 平台团队真正要负责的事情从头到尾亲手做一遍：landing zone、身份体系、CPU/GPU 混合算力、CI/CD、可复用的 AI 构建块、治理与成本控制。

## {{page.title}}
-----

这个服务本身做的事很简单：把音频转成文字，再对文字做摘要、做问答。简单是刻意的——应用层压得越薄，就越有余地深入到平台团队真正待着的那一层：别人的工作负载在这一层拿到身份、拿到算力、拿到一条铺好的发布路，以及一组想绕也绕不开的护栏。

### 它能做什么

* **带身份分级的转写。** 小号 Whisper 模型跑在常驻的 CPU 节点池上；大模型跑在 GPU 池上，而能不能用它，由 Microsoft Entra ID 的应用角色决定。没有对应角色却去请求贵的模型，API 直接返回 `403`，并告诉你缺哪个角色。
* **能缩到零的 GPU 池。** T4 节点只在有高级任务时才存在：一个挂起的 Pod 会把它唤醒（约五分钟），闲下来后节点自动消失。贵的硬件在没人用的时候，一分钱都不花。
* **带版本管理的提示词摘要。** 提示词以 YAML 形式纳入版本控制，而不是写死在代码里；每一次改动都要先过 CI 里的评估套件——检查忠实度、覆盖度、长度与结构。提示词一旦开始编造事实，构建就会失败。
* **一个 RAG 构建块。** 转写内容被切块、向量化，索引进 Azure AI Search；回答严格来自检索到的原文片段并附上出处，检索不到就明确拒答。
* **一个演示控制台。** API 自带一个网页界面，把这些平台侧的事实都摆到台面上：你是谁、你的角色解锁了哪些模型层级、GPU 节点此刻是热的还是已缩到零、每次 AI 调用消耗了多少 token、花了多少钱。

### 怎么搭的

所有基础设施都是代码（Bicep）：资源组、网络、监控、Key Vault、镜像仓库、存储、带多档报警的预算，以及一条**拒绝**未打标签资源组的 Azure Policy——让成本归属没有机会被慢慢侵蚀。治理是在工作负载之前部署的，不是事后补的。

我自己最满意的一点是：**整套系统里没有任何密钥**。GitHub Actions 通过 OIDC 联合身份登录 Azure；Kubernetes 里的 Pod 通过 workload identity 访问 Azure AI Foundry 和 AI Search；集群用托管身份拉取镜像。没有东西可泄露，也没有东西需要轮换。基于密钥的认证在服务层面就被关掉了，连"图省事"这条路都不存在。

### 踩过的坑

真正有意思的问题，都不是教程里写的那些。

有配额并不等于这个机型能用——集群拒绝了一个我明明有配额的节点规格，因为新订阅在那个区域只放行更新一代的 SKU；最后是区域选择跟着 GPU 配额走，而不是反过来。第一次 CI 跑失败，是因为 GitHub 现在签发的 OIDC token，subject 里用的是带数字 ID 的不可变格式，而不是文档里那个 `repo:owner/repo`——解决办法是去问身份提供方"你到底会发什么"，而不是照着文档假设。滚动更新在单节点上死锁过一次，因为默认策略要同时容纳新旧两个 Pod。还有一次例行部署差点唤醒一个要计费的 GPU 节点，因为重新 apply 清单会把副本数重置回去——现在它默认是 0，自动化再也不会在 GPU 上意外花钱。

单看每一件都是小事。合起来，这就是平台工作真实的质感：系统被写成什么样，和它实际怎么表现，中间那道缝。

### 技术栈

Azure · AKS · Bicep · Entra ID · Workload Identity · OIDC 联合身份 · GitHub Actions · Docker · Trivy · Azure AI Foundry · Azure AI Search · FastAPI · faster-whisper · OpenTelemetry · Application Insights

*这是一个学习性质的项目，借助 AI 协作完成，目的是把 AI 平台工程这个角色涉及的面都亲手摸一遍。其中的 Azure 资源、身份链路、流水线和各种取舍，都是真实的。*
