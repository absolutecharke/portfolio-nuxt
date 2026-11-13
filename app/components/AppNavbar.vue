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

function closeMenu() {
  isNavOpen.value = false
}
</script>

<template>
  <nav class="navbar custom-nav" @keydown.esc="closeMenu">
    <div class="navbar-inner">
      <NuxtLink class="navbar-brand" to="/" @click="closeMenu">Charles Pineda</NuxtLink>

      <button
        class="btn btn-ghost btn-square nav-toggle"
        type="button"
        aria-controls="portfolioNavbar"
        :aria-expanded="isNavOpen"
        :aria-label="isNavOpen ? 'Close navigation menu' : 'Open navigation menu'"
        @click="isNavOpen = !isNavOpen"
      >
        <svg
          v-if="!isNavOpen"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2.5"
          stroke-linecap="round"
        >
          <path d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg
          v-else
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2.5"
          stroke-linecap="round"
        >
          <path d="m6 6 12 12M18 6 6 18" />
        </svg>
      </button>

      <div
        id="portfolioNavbar"
        class="nav-links"
        :class="{ 'is-open': isNavOpen }"
      >
        <NuxtLink
          v-for="link in navLinks"
          :key="link.to"
          class="nav-link"
          exact-active-class="active"
          :to="link.to"
          @click="closeMenu"
        >
          {{ link.label }}
        </NuxtLink>
      </div>
    </div>
  </nav>
</template>
