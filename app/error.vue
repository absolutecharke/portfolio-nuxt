<script setup lang="ts">
import type { NuxtError } from '#app'

const props = defineProps<{
  error: NuxtError
}>()

const isNotFound = computed(() => props.error.statusCode === 404)

useHead({
  title: isNotFound.value ? '404 | Page Not Found' : 'Something went wrong',
})

function goHome() {
  clearError({ redirect: '/' })
}
</script>

<template>
  <main class="error-page">
    <section class="card error-card" aria-labelledby="error-title">
      <div class="card-body error-card-body">
        <p class="error-kicker">PORTFOLIO // SYSTEM MESSAGE</p>
        <p class="error-code">{{ isNotFound ? '404' : error.statusCode }}</p>
        <h1 id="error-title">
          {{ isNotFound ? 'Page not found' : 'Something went wrong' }}
        </h1>
        <p class="error-message">
          {{
            isNotFound
              ? "Looks like this page took a wrong turn. Let's get you back on track."
              : 'The page could not be loaded. Please head back to the home page.'
          }}
        </p>
        <button class="error-home-button" type="button" @click="goHome">
          Back to home
          <span aria-hidden="true">&rarr;</span>
        </button>
      </div>
    </section>
  </main>
</template>
