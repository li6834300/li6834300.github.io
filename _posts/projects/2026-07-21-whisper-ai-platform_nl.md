---
layout: post
title: "Whisper AI-platform — Self-service AI-transcriptie op Azure"
author: Zhien Li
category: projects
lang: nl
ref: whisper-ai-platform
tags:
  - content: Cloudplatform
  - content: AI/ML
  - content: DevOps
preview: projectImg/whisper-ai-platform.svg
align: align-left
urlLinks:
  - url: https://github.com/li6834300/learn_platform_whisper
    name: GitHub-repository
---

Ik heb een **self-service AI-transcriptieplatform op Azure** gebouwd — niet om een transcriptieproduct op te leveren, maar om praktisch door alles heen te werken waar een AI-platformteam werkelijk verantwoordelijk voor is: landing zones, identiteit, gemengde CPU/GPU-rekenkracht, CI/CD, herbruikbare AI-bouwblokken, governance en kostenbeheersing.

## {{page.title}}
-----

De dienst zelf doet iets eenvoudigs: audio omzetten naar tekst, die tekst samenvatten en er vragen over beantwoorden. Die eenvoud is een bewuste keuze. Door de applicatie klein te houden bleef er ruimte om de diepte in te gaan waar een platformteam daadwerkelijk zit — in de laag *onder* de applicatie, waar de workloads van anderen hun identiteit, hun rekenkracht, een geëffend uitrolpad en vangrails krijgen waar je niet per ongeluk omheen kunt.

### Wat het doet

* **Transcriptie met identiteitsgestuurde niveaus.** Kleine Whisper-modellen draaien op een CPU-nodepool die altijd aanstaat. Het grote model draait op een GPU-pool — en toegang daartoe wordt bepaald door een app-rol in Microsoft Entra ID. Vraag je het dure model op zonder de juiste rol, dan geeft de API een `403` terug, mét uitleg welke rol je nodig zou hebben.
* **Een GPU-pool die naar nul schaalt.** De T4-node bestaat alleen zolang er premiumwerk draait. Een wachtende pod wekt hem (ongeveer vijf minuten) en hij verdwijnt weer zodra het stil wordt, zodat dure hardware in rust niets kost.
* **Samenvatten met geversioneerde prompts.** Prompts staan in YAML onder versiebeheer, niet in de code, en elke wijziging wordt in CI afgevangen door een evaluatiesuite die betrouwbaarheid, dekking, lengte en structuur controleert. Een prompt die feiten begint te verzinnen, laat de build falen.
* **Een RAG-bouwblok.** Transcripties worden opgeknipt, ge-embed en geïndexeerd in Azure AI Search; vragen worden uitsluitend beantwoord op basis van de opgehaalde passages, mét bronvermelding — en geweigerd wanneer het antwoord er niet in staat.
* **Een democonsole.** De API serveert een kleine webinterface die dit alles zichtbaar maakt: wie je bent, welke modelniveaus jouw rollen ontsluiten, of de GPU-node op dit moment warm is of naar nul geschaald, en hoeveel tokens en geld elke AI-aanroep kost.

### Hoe het gebouwd is

Alles is infrastructure as code (Bicep): resourcegroep, netwerk, monitoring, Key Vault, containerregistry, opslag, een budget met gelaagde waarschuwingen, en een Azure Policy die resourcegroepen zonder tags *weigert*, zodat kostentoerekening niet stilletjes kan verwateren. Governance wordt vóór de workloads uitgerold, niet er achteraf op geschroefd.

Waar ik het meest tevreden over ben: **er zitten nergens secrets in het systeem**. GitHub Actions authenticeert bij Azure via OIDC-federatie; de Kubernetes-pods bereiken Azure AI Foundry en AI Search via workload identity; het cluster haalt images op met zijn managed identity. Niets dat kan uitlekken, niets dat geroteerd hoeft te worden. Authenticatie met sleutels staat op serviceniveau uit, dus het is niet eens beschikbaar als sluiproute.

### Wat ik geleerd heb

De interessante problemen stonden niet in de handleidingen.

Beschikbare quota bleek niet hetzelfde als een beschikbare VM-grootte — het cluster weigerde een nodetype waarvoor ik quota hád, omdat nieuwe abonnementen in die regio alleen nieuwere SKU-generaties krijgen. Uiteindelijk volgde de regiokeuze het GPU-quotum in plaats van andersom. Mijn eerste CI-run faalde omdat GitHub OIDC-tokens tegenwoordig uitgeeft met onveranderlijke numerieke identifiers in de subject-claim, en niet in de gedocumenteerde `repo:owner/repo`-vorm; de oplossing was de identity provider te vrágen wat hij werkelijk stuurt in plaats van het aan te nemen. Een rolling update liep vast op één kleine node, omdat de standaardstrategie ruimte wil voor de oude én de nieuwe pod tegelijk. En een routinematige deployment wekte bijna een GPU-node die geld kost, doordat het opnieuw toepassen van de manifesten het aantal replica's terugzette — dat staat nu standaard op nul, zodat automatisering nooit per ongeluk aan GPU's kan uitgeven.

Stuk voor stuk kleinigheden. Bij elkaar zijn ze precies de textuur van platformwerk: het gat tussen hoe een systeem gedocumenteerd staat en hoe het zich gedraagt.

### Stack

Azure · AKS · Bicep · Entra ID · Workload Identity · OIDC-federatie · GitHub Actions · Docker · Trivy · Azure AI Foundry · Azure AI Search · FastAPI · faster-whisper · OpenTelemetry · Application Insights

*Gebouwd als leerproject, met hulp van AI, om praktisch kennis te maken met het volledige werkveld van een AI-platformengineer. De Azure-resources, identiteitsstromen, pipelines en afwegingen zijn allemaal echt.*
