<script setup>
import { ref } from 'vue'

const activeProject = ref(null)

const skills = [
  'Java', 'Spring Boot', 'Python', 'Vue 3', 'TypeScript',
  'JavaScript', 'MongoDB', 'MySQL', 'REST APIs', 'Python ETL',
  'Docker', 'Apache Superset', 'Git', 'HTML', 'CSS'
]

const projects = [
  {
    title: 'FreshKatch Reporting & Analytics',
    type: 'Full Stack • Data & Analytics',
    description: 'Built and integrated a reporting flow that connects application data with Python ETL, MySQL reporting data and Apache Superset dashboards.',
    points: [
      'Integrated Apache Superset dashboards into the FreshKatch application.',
      'Worked on revenue and business analytics charts, dashboard filters and embedded reporting.',
      'Worked with MongoDB → Python ETL → MySQL reporting flow.',
      'Investigated incremental refresh and new-order data update behavior.',
      'Worked with Docker-based Superset setup and configuration.'
    ],
    stack: ['Vue 3', 'TypeScript', 'Spring Boot', 'MongoDB', 'Python', 'MySQL', 'Superset', 'Docker']
  },
  {
    title: 'HTP Website',
    type: 'Full Stack Web Application',
    description: 'Worked across the HTP web application on multiple functional pages and application flows.',
    points: [
      'Built and improved the Consumables page.',
      'Worked on Datalogger and Recipe pages.',
      'Implemented and refined login/authentication flow.',
      'Integrated frontend screens with backend APIs.',
      'Worked on validations, UI behavior and functional fixes.'
    ],
    stack: ['Vue 3', 'TypeScript', 'Spring Boot', 'MongoDB', 'REST API']
  },
  {
    title: 'Food Party',
    type: 'Full Stack Project',
    description: 'A web-based food management system with a React frontend, Python backend and MySQL database.',
    points: [
      'Implemented sign-in and sign-out functionality.',
      'Added and deleted food items through the application.',
      'Created a responsive frontend using HTML and CSS.',
      'Connected frontend, backend and MySQL for dynamic data management.'
    ],
    stack: ['React', 'Python', 'MySQL', 'HTML', 'CSS']
  }
]

const experience = [
  {
    title: 'Full Stack Development & Reporting',
    company: 'Current Project Work',
    text: 'Working on production-style web application features, backend integration, ETL/reporting workflows and embedded analytics dashboards.'
  },
  {
    title: 'Python Developer Internship',
    company: 'Internship',
    text: 'Gained hands-on experience with Tkinter, debugging, troubleshooting, web scraping, error handling, REST APIs and Python packages.'
  }
]

function scrollToId(id) {
  document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<template>
  <div class="app-shell">
    <header class="nav">
      <button class="brand" @click="scrollToId('home')">SS<span>.</span></button>
      <nav>
        <button @click="scrollToId('about')">About</button>
        <button @click="scrollToId('skills')">Skills</button>
        <button @click="scrollToId('projects')">Projects</button>
        <button @click="scrollToId('experience')">Experience</button>
        <button @click="scrollToId('contact')">Contact</button>
      </nav>
      <a class="nav-cta" href="/resume.pdf" target="_blank">Resume ↗</a>
    </header>

    <main>
      <section id="home" class="hero section">
        <div class="hero-copy">
          <p class="eyebrow">FULL STACK DEVELOPER · DATA & ANALYTICS</p>
          <h1>Hi, I'm <span>Sanjay.</span><br />I build useful digital products.</h1>
          <p class="hero-text">
            Developer focused on web applications, backend services, data pipelines
            and analytics dashboards. I enjoy turning real business requirements into
            working, maintainable software.
          </p>
          <div class="hero-actions">
            <button class="primary" @click="scrollToId('projects')">View my work <b>→</b></button>
            <button class="secondary" @click="scrollToId('contact')">Let's connect</button>
          </div>
          <div class="quick-stats">
            <div><strong>15+</strong><span>Technologies</span></div>
            <div><strong>3</strong><span>Featured projects</span></div>
            <div><strong>∞</strong><span>Learning mindset</span></div>
          </div>
        </div>
        <div class="hero-card">
          <div class="code-window">
            <div class="window-bar"><i></i><i></i><i></i><span>developer.ts</span></div>
            <pre><code><em>const</em> sanjay = {
  role: <strong>"Full Stack Developer"</strong>,
  frontend: [<strong>"Vue"</strong>, <strong>"TypeScript"</strong>],
  backend: [<strong>"Java"</strong>, <strong>"Spring Boot"</strong>],
  data: [<strong>"MongoDB"</strong>, <strong>"MySQL"</strong>],
  analytics: <strong>"Superset"</strong>,
  tools: [<strong>"Python"</strong>, <strong>"Docker"</strong>]
}</code></pre>
          </div>
          <div class="floating-chip">● Available to build</div>
        </div>
      </section>

      <section id="about" class="section split">
        <div>
          <p class="eyebrow">01 · ABOUT</p>
          <h2>From Python beginnings to full-stack product work.</h2>
        </div>
        <div class="section-text">
          <p>
            I'm a developer with a foundation in Python and databases, now working
            across frontend, backend and reporting systems. My recent work includes
            Vue-based application pages, Spring Boot APIs, MongoDB, MySQL reporting,
            Python ETL and embedded Apache Superset analytics.
          </p>
          <p>
            I like understanding the complete flow — from a user's screen and API
            request to database changes, ETL processing and the final dashboard.
          </p>
        </div>
      </section>

      <section id="skills" class="section">
        <div class="section-heading">
          <div><p class="eyebrow">02 · SKILLS</p><h2>My toolkit.</h2></div>
          <p>Technologies I've worked with across application development and analytics.</p>
        </div>
        <div class="skill-grid">
          <span v-for="skill in skills" :key="skill">{{ skill }}</span>
        </div>
      </section>

      <section id="projects" class="section projects-section">
        <div class="section-heading">
          <div><p class="eyebrow">03 · PROJECTS</p><h2>Selected work.</h2></div>
          <p>Recent development work plus my earlier full-stack project.</p>
        </div>
        <div class="project-grid">
          <article v-for="(project, index) in projects" :key="project.title" class="project-card">
            <div class="project-number">0{{ index + 1 }}</div>
            <p class="project-type">{{ project.type }}</p>
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="tags">
              <span v-for="tag in project.stack" :key="tag">{{ tag }}</span>
            </div>
            <button class="project-link" @click="activeProject = project">View details <b>↗</b></button>
          </article>
        </div>
      </section>

      <section id="experience" class="section">
        <div class="section-heading">
          <div><p class="eyebrow">04 · EXPERIENCE</p><h2>What I've been working on.</h2></div>
        </div>
        <div class="timeline">
          <article v-for="item in experience" :key="item.title" class="timeline-item">
            <div class="timeline-dot"></div>
            <div>
              <p class="project-type">{{ item.company }}</p>
              <h3>{{ item.title }}</h3>
              <p>{{ item.text }}</p>
            </div>
          </article>
        </div>
      </section>

      <section id="education" class="section education">
        <div>
          <p class="eyebrow">05 · EDUCATION & CERTIFICATIONS</p>
          <h2>Foundation + continuous learning.</h2>
        </div>
        <div class="edu-card">
          <h3>Bachelor of Arts — Economics</h3>
          <p>The American College, Madurai · 2024</p>
          <small>Overall percentage: 75.4%</small>
        </div>
        <div class="edu-card">
          <h3>Python Course Completion</h3>
          <p>Python programming, data structures, algorithms, database management and SQL integration.</p>
        </div>
        <div class="edu-card">
          <h3>Python Developer Internship Completion</h3>
          <p>Tkinter, debugging, troubleshooting, web scraping, error handling, REST APIs and Python packages.</p>
        </div>
      </section>

      <section id="contact" class="section contact">
        <p class="eyebrow">06 · CONTACT</p>
        <h2>Have a project in mind?</h2>
        <p>Let's connect and build something useful.</p>
        <div class="contact-actions">
          <a class="primary" href="mailto:sanjaycreater333@gmail.com">Email me →</a>
          <a class="secondary" href="https://github.com/sanjay9361" target="_blank" rel="noreferrer">GitHub ↗</a>
          <a class="secondary" href="https://www.linkedin.com/in/sanjay-s-09930534" target="_blank" rel="noreferrer">LinkedIn ↗</a>
        </div>
      </section>
    </main>

    <footer>
      <span>© 2026 Sanjay Senthilkumar</span>
      <span>Built with Vue 3</span>
    </footer>

    <div v-if="activeProject" class="modal-backdrop" @click.self="activeProject = null">
      <div class="modal">
        <button class="close" @click="activeProject = null">×</button>
        <p class="project-type">{{ activeProject.type }}</p>
        <h2>{{ activeProject.title }}</h2>
        <p>{{ activeProject.description }}</p>
        <ul>
          <li v-for="point in activeProject.points" :key="point">{{ point }}</li>
        </ul>
        <div class="tags"><span v-for="tag in activeProject.stack" :key="tag">{{ tag }}</span></div>
      </div>
    </div>
  </div>
</template>