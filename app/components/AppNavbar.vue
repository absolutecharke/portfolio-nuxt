<script setup>
const route = useRoute()
const isNavOpen = ref(false)

const navLinks = [
  { label: 'Home', to: '/' },
  { label: 'About', to: '/about' },
  { label: 'Tech Stack', to: '/tech-stack' },
  { label: 'Certifications', to: '/certificates' },
]

watch(() => route.path, () => {
  isNavOpen.value = false
})
</script>

<template>
  <nav class="navbar navbar-expand-md fixed-top custom-nav">
    <div class="container-fluid px-3">
      <NuxtLink class="navbar-brand" to="/">Portfolio</NuxtLink>

      <button
        class="navbar-toggler"
        type="button"
        aria-controls="portfolioNavbar"
        :aria-expanded="isNavOpen"
        aria-label="Toggle navigation"
        @click="isNavOpen = !isNavOpen"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div
        id="portfolioNavbar"
        class="navbar-collapse"
        :class="{ show: isNavOpen }"
      >
        <div class="navbar-nav ms-auto">
          <NuxtLink
            v-for="link in navLinks"
            :key="link.to"
            class="nav-link"
            exact-active-class="active"
            :to="link.to"
          >
            {{ link.label }}
          </NuxtLink>
        </div>
      </div>
    </div>
  </nav>
</template>
