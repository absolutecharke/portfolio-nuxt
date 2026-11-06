<script setup>
useHead({ title: 'Tech Stack | Portfolio' })

// Images in public/images are served from /images.
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

// TODO: your old main.js (Anime.js / SweetAlert2 logic) was not included,
// so its behavior isn't ported yet. Call it from here, e.g.:
function onItemClick(tech) {
  // showTechAlert(tech.name)
}
</script>

<template>
  <div class="page active">
    <div class="section-title">Languages &amp; Frameworks</div>
    <div class="stack-grid">
      <div
        v-for="tech in languages"
        :key="tech.name"
        class="stack-item"
        :data-tech="tech.name"
        @click="onItemClick(tech)"
      >
        <div class="stack-icon"><img :src="tech.icon" :alt="`${tech.name} icon`" /></div>
        {{ tech.name }}
      </div>
    </div>

    <div class="section-title">Tools &amp; Platforms</div>
    <div class="stack-grid">
      <div
        v-for="tech in tools"
        :key="tech.name"
        class="stack-item"
        :data-tech="tech.name"
        @click="onItemClick(tech)"
      >
        <div class="stack-icon"><img :src="tech.icon" :alt="`${tech.name} icon`" /></div>
        {{ tech.name }}
      </div>
    </div>
  </div>
</template>