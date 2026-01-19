---
layout: page
title: Zhien Li
permalink: /about/
---

<style>
.resume-header {
  text-align: left;
  margin-bottom: 30px;
}

.resume-header h2 {
  margin: 10px 0;
  font-size: 2em;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
}

.resume-header p {
  margin: 5px 0;
  color: #666;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
}

.tab-container {
  margin: 30px 0;
}

.tab-buttons {
  display: inline-flex;
  background: #e8e5f0;
  border-radius: 50px;
  padding: 6px;
  margin-bottom: 40px;
  box-shadow: 0 2px 8px rgba(125, 114, 179, 0.1);
  position: relative;
  left: 50%;
  transform: translateX(-50%);
}

.tab-button {
  padding: 12px 32px;
  background: transparent;
  border: none;
  cursor: pointer;
  font-size: 15px;
  font-weight: 500;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  color: #7d72b3;
  opacity: 0.6;
  transition: all 0.3s ease-in-out;
  border-radius: 50px;
  position: relative;
  z-index: 1;
  white-space: nowrap;
  display: flex;
  align-items: center;
  justify-content: center;
}

.tab-button:hover {
  opacity: 0.8;
}

.tab-button.active {
  background: white;
  color: #7d72b3;
  opacity: 1;
  box-shadow: 0 2px 8px rgba(125, 114, 179, 0.15);
}

.tab-content {
  display: none;
}

.tab-content.active {
  display: block;
  animation: fadeIn 0.3s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.section-title {
  color: #7d72b3;
  border-bottom: 2px solid #e8e5f0;
  padding-bottom: 5px;
  margin-top: 30px;
  margin-bottom: 20px;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
}

.experience-item, .education-item, .project-item {
  margin-bottom: 25px;
}

.experience-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 10px;
  flex-wrap: nowrap;
  gap: 15px;
}

.experience-title {
  font-weight: bold;
  font-size: 0.95em;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  flex-shrink: 1;
  min-width: 0;
}

.experience-date {
  color: #666;
  font-size: 0.85em;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  white-space: nowrap;
  flex-shrink: 0;
}

.publication-item {
  margin-bottom: 15px;
  padding-left: 20px;
  position: relative;
}

.publication-item::before {
  content: "•";
  position: absolute;
  left: 0;
  font-weight: bold;
  color: #7d72b3;
}

.tab-content h2 {
  color: #7d72b3;
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  font-size: 1.8em;
  margin-top: 30px;
  margin-bottom: 15px;
}

.tab-content p {
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  line-height: 1.6;
  color: #333;
}

.tab-content ul {
  font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
  line-height: 1.6;
}

.tab-content a {
  color: #7d72b3;
  text-decoration: none;
  transition: all 0.2s ease-in-out;
}

.tab-content a:hover {
  color: #9b8fd6;
  text-decoration: underline;
}

.tab-content hr {
  border: none;
  border-top: 1px solid #e8e5f0;
  margin: 30px 0;
}

.tab-content strong {
  color: #7d72b3;
  font-weight: 600;
}
</style>

<div class="resume-header">
  <p>Petrus Gaginistraat 51, 6217GG, Maastricht, Netherlands</p>
  <p>+31 0613085599 | <a href="mailto:kenli@nyu.edu">kenli@nyu.edu</a> | Site: <a href="https://www.lizhien.me">www.lizhien.me</a></p>
</div>

<div class="tab-container">
  <div class="tab-buttons">
    <button class="tab-button active" onclick="switchTab('academic')">Academic Me</button>
    <button class="tab-button" onclick="switchTab('engineer')">Software Engineer Me</button>
  </div>

  <!-- Academic Tab -->
  <div id="academic" class="tab-content active">

<h2>Profile Summary</h2>

<p>I am a learning science researcher and instructional designer with background in medical education and digital media. Experienced in developing simulation-based experience and technology-enhanced solution. Current doctoral research focuses on instructional design for knowledge acquisition and transfer through authentic cases and peer dialogue in medical and health professions simulation education.</p>

<hr>

<h2>Education</h2>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Ph.D. Candidate in Education Technology | Maastricht University</span>
  <span class="experience-date">JUNE 2022 – PRESENT</span>
</div>
<ul>
<li><strong>Research Focus</strong>: Instructional Design, Virtual Patients (VPs), Learning Science, Education Technologies, Feedback.</li>
<li><strong>Thesis</strong>: Investigating the Integration of VPs in class to foster knowledge acquisition and transfer.</li>
</ul>
</div>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Master of Science in Digital Media | New York University | GPA 3.85 / 4</span>
  <span class="experience-date">MAY 2013</span>
</div>
<ul>
<li><strong>Key coursework</strong>: Game Design, HCI/User Experience, Media Study, Web Development, Video for New Media.</li>
</ul>
</div>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Bachelor in Broadcast Engineering | Communication University of China in Nanjing | GPA 3.23 / 4</span>
  <span class="experience-date">JUN 2010</span>
</div>
<ul>
<li><strong>Minor</strong>: Public Relationship & Marketing</li>
</ul>
</div>

<hr>

<h2>Publications</h2>

<div class="publication-item">
Li, Z., et al. (2024). <em>Perception of enhanced learning in medicine through integration of VPs.</em> <strong>BMC Medical Education.</strong>
</div>

<div class="publication-item">
Li, Z., et al. (under review). <em>Enhancing Clinical Reasoning with VPs: The Role of "What-If" Discussions.</em> <strong>Medical Education</strong>
</div>

<div class="publication-item">
Li, Z., et al. (under review). <em>How feedback discussions influence medical students' clinical reasoning skill.</em> <strong>Medical Teacher</strong>
</div>

<div class="publication-item">
Li, Z., et al. (in preparation) <em>Contextualized learning empowered by peer dialogue: A Intervention in Biology and Health.</em>
</div>

<p>Another 5 publications available at ORCID: <a href="https://orcid.org/0009-0007-2223-8940">https://orcid.org/0009-0007-2223-8940</a></p>

<hr>

<h2>Conference Presentations & Awards</h2>

<ul>
<li><strong>Best Presentation Award</strong>, International Health Professions Education Virtual Conference, 2024.</li>
<li><strong>Paper Presentation</strong>: The Role of "What-If" Discussions, AMEE Conference, 2025.</li>
<li><strong>Paper Presentation</strong>: How feedback discussions influence clinical reasoning skills, EARLI Conference, 2025.</li>
<li><strong>Second Place</strong>, Brightlands Startup Challenge – Overstep: AI-assisted learning tool, 2024.</li>
<li><strong>NYU High GPA Schoolarship Reward</strong> (3000$ x 2 times)</li>
<li><strong>Recognized CTB Research Coach</strong>, China Think Big competition.</li>
<li><strong>Code.org Certified CS teacher</strong> (Microsoft-led online CS teaching platform).</li>
<li><strong>Xiamen Backbone Software Engineer</strong></li>
</ul>

<hr>

<h2>Project & Experience</h2>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">CS TEACHER, LMS MANAGER, COORDINATOR | FARRAGUT ACADEMY DONGGUAN</span>
  <span class="experience-date">JUN 2020 TO JUN 2022</span>
</div>
<p><em>Admiral Farragut Academy Dongguan is Chinese branch of an American high school headquartered in Tampa, FL</em></p>
<ul>
<li>Designed and taught Computer Science curriculum for Grades 6–12, including AP-level content.</li>
<li>Introduced SRL techniques to Grade 12, focusing on goal setting, time management, and metacognition.</li>
<li>Incorporated PBL, gig saw and peer collaboration strategies, helping students develop problem-solving and entrepreneurial skills.</li>
<li>Coached China Think Big (CTB) research competition teams, achieving a national third-place award.</li>
<li>Managed various digital learning platforms (Xiaobao, Gradelink, myON, and Code.org) and developed data-driven e-portfolio systems for academic tracking.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">ACADEMIC PROJECTS IN NEW YORK UNIVERSITY</span>
  <span class="experience-date">JAN 2012 TO MAY 2013</span>
</div>
<ul>
<li><strong>3D Earthquake Data Visualization</strong>: Built a real-time earthquake data visualization in Unity 3D using USGS data; utilized joystick and Leap Motion for HCI exploration research.</li>
<li><strong>VR Campus Experience</strong>: Recreated NYU Engineering campus in Unity for an immersive navigation experience.</li>
<li><strong>Motion-Controlled Webcam Game</strong>: Built an accessible Java-based interaction prototype using simple color cues.</li>
<li><strong>Accelerometer-Based Arduino Game</strong>: Showcased at NY Game Expo 2012; Created a playful alternative interaction methods.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">SENIOR FRONT-END ENGINEER | RINGCENTRAL CORP (NYSE: RNG)</span>
  <span class="experience-date">OCT 2015 TO JUN 2020</span>
</div>
<ul>
<li>Built and maintained enterprise-level front-end features (React.js, Angular.js).</li>
<li>Implemented internationalization (i18n) for multilingual product deployment.</li>
<li>Collaborated with cross-functional teams to enhance user experience and platform stability.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">WEB DEVELOPER | CITI GROUP (NYSE: C) | BUFFALO, NY</span>
  <span class="experience-date">APR 2014 TO JUL 2015</span>
</div>
<ul>
<li>Maintained financial web content and newsletters ensuring branding and accessibility standards.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">WEB DEVELOPER | EVOLVING TECHNOLOGIES CORPORATION | BROOKLYN, NY</span>
  <span class="experience-date">JUL 2012 TO FEB 2014</span>
</div>
<ul>
<li>Developed collaborative visualization (like Google Doc) and data negotiation tools using JavaScript (jQuery).</li>
</ul>
</div>

<hr>

<h2>Skills & Expertise</h2>

<ul>
<li><strong>Instructional Design</strong>: Instructional design, simulation-based learning, cognitive load, knowledge transfer, qualitative & mixed-methods research.</li>
<li><strong>Technical Proficiency</strong>: All type of programming languages (like Python, JavaScript, React, H5, CSS) Unity, AI tool prototyping, data visualization.</li>
<li><strong>Teaching</strong>: Computer Science, Digital Media.</li>
</ul>

<hr>

<div style="background: #f8f7fc; padding: 20px; border-radius: 8px; border-left: 4px solid #7d72b3; margin-top: 30px;">
<p style="margin: 0; font-style: italic; color: #555;">I am currently actively looking for a position in the Netherlands in academia or educational software development. I believe there is a big change on how people learn and how we should implement tools for learning. If you would like to change the educational world with me, shoot me an email at <a href="mailto:kenli@nyu.edu">kenli@nyu.edu</a> or <a href="mailto:zhien.li@maastrichtuniversity.nl">zhien.li@maastrichtuniversity.nl</a>.</p>
</div>

  </div>

  <!-- Software Engineer Tab -->
  <div id="engineer" class="tab-content">

<h2>Profile Summary</h2>

<p>Full-stack / front-end software engineer with 8+ years of professional experience in large-scale product development (React, Angular, JavaScript, Python) and a strong background in HCI, UX, and interactive system design. Experienced in building scalable web applications, internationalization (i18n), and cross-team collaboration. Recent work includes AI-assisted learning tools and simulation-based educational applications. Bringing a hybrid background in software engineering + digital media + educational technology, with the ability to design, build, and ship user-focused products.</p>

<hr>

<h2>Skills & Expertise</h2>

<ul>
<li><strong>Languages</strong>: JavaScript (ES6+), TypeScript, Python, HTML5, CSS3, SQL, Mongo.</li>
<li><strong>Frameworks & Libraries</strong>: React.js, Angular.js, Vue.js, Node.js, Flask</li>
<li><strong>Tools</strong>: Git, Webpack, Docker, Jira, CI/CD</li>
<li><strong>Specialties</strong>: Front-end architecture, i18n, UX prototyping, AI-assisted tools, Web performance optimization</li>
<li><strong>Other</strong>: Unity3D, Data visualization, LMS integrations, EdTech product design</li>
</ul>

<hr>

<h2>Professional Experience</h2>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">CO-FOUNDER & ENGINEER | QINGREN EDU TECH CORP | DONGGUAN, CN</span>
  <span class="experience-date">JUN 2020 TO JUN 2022</span>
</div>
<ul>
<li>Developed School Management system and student report system.</li>
<li>Collaborate with secondary school teachers to develop a level-based reading platform.</li>
<li>Teach Computer Science</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">SENIOR FRONT-END ENGINEER | RINGCENTRAL CORP (NYSE: RNG) | XIAMEN, CN</span>
  <span class="experience-date">OCT 2015 TO JUN 2020</span>
</div>
<ul>
<li>Developed and maintained front-end features for a global enterprise communication platform (think of Teams) used by millions of users.</li>
<li>Built complex UI components with React.js in a large modular codebase.</li>
<li>Implemented global internationalization (i18n) infrastructure enabling multi-market product release.</li>
<li>Collaborated with designers, backend teams, and product managers across distributed teams with Scrum flow.</li>
<li>Improved UI performance and reduced load time through code splitting and caching strategies.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">WEB DEVELOPER | CITI GROUP (NYSE: C) | BUFFALO, NY</span>
  <span class="experience-date">APR 2014 TO JUL 2015</span>
</div>
<ul>
<li>Maintained and updated financial web portals under strict branding and security guidelines.</li>
<li>Built reusable UI components and content templates to support fast iteration cycles.</li>
<li>Coordinated with QA and design teams to ensure accessibility and cross-browser compatibility.</li>
</ul>
</div>

<div class="experience-item">
<div class="experience-header">
  <span class="experience-title">WEB DEVELOPER | EVOLVING TECHNOLOGIES CORPORATION | BROOKLYN, NY</span>
  <span class="experience-date">JUL 2012 TO FEB 2014</span>
</div>
<ul>
<li>Built collaborative data-negotiation tools (think of google doc) using JavaScript (jQuery, JSPlumb, Gridster).</li>
<li>Developed real-time interactive interfaces for remote teams.</li>
<li>Contributed to UX and workflow design for internal productivity apps.</li>
</ul>
</div>

<hr>

<h2>Other Projects</h2>

<ul>
<li><strong>Overstep</strong>, an AI based language learning tool. Fully self-developed, allow user to learn any language from any mother tone.</li>
<li>Several game developments with Unity and RPG Maker.</li>
<li>Build websites, brand with help of AI (go to <a href="https://lizhien.me/">https://lizhien.me/</a> to see works)</li>
</ul>

<hr>

<h2>Selected Rewards</h2>

<ul>
<li><strong>Best Presentation Award</strong>, International Health Professions Education Virtual Conference, 2024.</li>
<li><strong>Paper Presentation</strong>: The Role of "What-If" Discussions, AMEE Conference, 2025.</li>
<li><strong>Paper Presentation</strong>: How feedback discussions influence clinical reasoning skills, EARLI Conference, 2025.</li>
<li><strong>Second Place</strong>, Brightlands Startup Challenge – Overstep: AI-assisted learning tool, 2024.</li>
<li><strong>NYU High GPA Schoolarship Reward</strong> (3000$ x 2 times)</li>
<li><strong>Recognized CTB Research Coach</strong>, China Think Big competition.</li>
<li><strong>Code.org Certified CS teacher</strong> (Microsoft-led online CS teaching platform).</li>
<li><strong>Xiamen Backbone Software Engineer</strong></li>
</ul>

<hr>

<h2>Education</h2>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Ph.D. Candidate in Education Technology | Maastricht University</span>
  <span class="experience-date">JUN 2022 – PRESENT</span>
</div>
<ul>
<li><strong>Research Focus</strong>: Virtual Patients (VPs), Learning Science, Education Technologies, Instructional Design, Feedback.</li>
<li><strong>Thesis</strong>: Investigating the Integration of VPs in class to foster knowledge acquisition and transfer.</li>
</ul>
</div>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Master of Science in Digital Media | New York University | GPA 3.85 / 4</span>
  <span class="experience-date">MAY 2013</span>
</div>
<ul>
<li><strong>Key coursework</strong>: Game Design, HCI/User Experience, Media Study, Web Development, Video for New Media.</li>
</ul>
</div>

<div class="education-item">
<div class="experience-header">
  <span class="experience-title">Bachelor in Broadcast Engineering | Communication University of China in Nanjing | GPA 3.23 / 4</span>
  <span class="experience-date">JUN 2010</span>
</div>
<ul>
<li><strong>Minor</strong>: Public Relationship & Marketing</li>
</ul>
</div>

<hr>

<div style="background: #f8f7fc; padding: 20px; border-radius: 8px; border-left: 4px solid #7d72b3; margin-top: 30px;">
<p style="margin: 0; font-style: italic; color: #555;">I am currently actively looking for a position in the Netherlands in academia or educational software development. I believe there is a big change on how people learn and how we should implement tools for learning. If you would like to change the educational world with me, shoot me an email at <a href="mailto:kenli@nyu.edu">kenli@nyu.edu</a> or <a href="mailto:zhien.li@maastrichtuniversity.nl">zhien.li@maastrichtuniversity.nl</a>.</p>
</div>

  </div>
</div>

<script>
function switchTab(tabName) {
  // Hide all tab contents
  const tabContents = document.querySelectorAll('.tab-content');
  tabContents.forEach(content => {
    content.classList.remove('active');
  });

  // Remove active class from all buttons
  const tabButtons = document.querySelectorAll('.tab-button');
  tabButtons.forEach(button => {
    button.classList.remove('active');
  });

  // Show selected tab content
  document.getElementById(tabName).classList.add('active');

  // Add active class to clicked button
  event.target.classList.add('active');
}
</script>  
