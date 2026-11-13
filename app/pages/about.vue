<script setup>
import { useSeoMeta } from '#imports' 

useSeoMeta({
  title: 'About Me - Charles Pineda | IT Portfolio',
  description: 'Learn more about Charles Pineda, an IT student passionate about cybersecurity, database management, and game development.',
  
  ogTitle: 'About Charles Pineda - IT Student & Aspiring Developer',
  ogDescription: 'Discover Charles Pineda background, hobbies like reading comics and running, and career aspirations in cybersecurity and game dev.',
  ogType: 'website',
})
</script>

<template>
  <div class="page active">
    <div class="section-title">About me</div>

    <div class="card portfolio-card highlight-grid">
      <div class="card-body portfolio-card-body">
        <h3>Who I am</h3>
        <p>
          "I'm Charles Pineda, an IT student passionate about building a future in the IT industry.
          I specialize in surface-level database coding and enjoy creating projects that are both
          fun and engaging. Outside of technology, I spend my time reading comics, collecting
          action figures, playing instruments, running, and staying active at the gym, which
          helps me stay creative, disciplined, and motivated."
        </p>
      </div>
    </div>

    <div class="card portfolio-card highlight-grid">
      <div class="card-body portfolio-card-body">
        <h3>My Aspirations</h3>
        <p>
          "I aspire to have a position in IT department professions I want to professionalize in
          like cyber security, database management, game development, and such. I love collaborating
          on new ideas and turning concepts into interactive experiences. My focus is on learning
          by doing, improving my skills with every project, and sharing my enthusiasm for
          technology through creative work."
        </p>
      </div>
    </div>
  </div>
</template>