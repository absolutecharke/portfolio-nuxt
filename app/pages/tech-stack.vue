<script setup>
import { useSeoMeta } from '#imports'

useSeoMeta({
  title: 'Tech Stack - Charles Pineda | IT Portfolio',
  description: 'Explore the programming languages, frameworks, databases, and developer tools used by Charles Pineda in software engineering and web development projects.',
  ogTitle: 'Tech Stack & Skills - Charles Pineda | Portfolio',
  ogDescription: 'Discover the languages (HTML, CSS, JavaScript, Java, MySQL, PostgreSQL) and tools (Git, GitHub, VS Code) in Charles Pineda\'s developer toolkit.',
  ogType: 'website',
})


const languages = [
  { name: 'HTML', icon: '/images/htmllll.webp' },
  { name: 'CSS', icon: '/images/css-3.svg' },
  { name: 'JavaScript', icon: '/images/javascript-icon.webp' },
  { name: 'Java', icon: '/images/jaavvaa.png' },
  { name: 'MySQL', icon: '/images/mysqql.png' },
  { name: 'PostgreSQL', icon: '/images/postgresql.png' },
]

const tools = [
  { name: 'Git', icon: '/images/git.png' },
  { name: 'GitHub', icon: '/images/github.png' },
  { name: 'VS Code', icon: '/images/vscode.png' },
]

</script>

<template>
  <div class="page active">
    <div class="section-title">Languages &amp; Frameworks</div>
    <div class="stack-grid">
      <article
        v-for="tech in languages"
        :key="tech.name"
        class="card portfolio-card stack-item"
      >
        <div class="card-body portfolio-card-body">
          <div class="stack-icon"><img :src="tech.icon" :alt="`${tech.name} icon`" /></div>
          <h3 class="card-title stack-name">{{ tech.name }}</h3>
        </div>
      </article>
    </div>

    <div class="section-title">Tools &amp; Platforms</div>
    <div class="stack-grid">
      <article
        v-for="tech in tools"
        :key="tech.name"
        class="card portfolio-card stack-item"
      >
        <div class="card-body portfolio-card-body">
          <div class="stack-icon"><img :src="tech.icon" :alt="`${tech.name} icon`" /></div>
          <h3 class="card-title stack-name">{{ tech.name }}</h3>
        </div>
      </article>
    </div>
  </div>
</template>