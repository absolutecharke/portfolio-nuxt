<script setup>
import { ref, watch, onMounted, onBeforeUnmount } from 'vue'
import { useSeoMeta } from '#imports'

useSeoMeta({
  title: 'Certifications - Charles Pineda | IT Portfolio',
  description: 'View professional certifications earned by Charles Pineda, including Python Essentials and Networking Basics from Cisco Networking Academy.',
  
  ogTitle: 'Professional Certifications - Charles Pineda | Portfolio',
  ogDescription: 'Explore verified IT certifications from Cisco Networking Academy earned by Charles Pineda.',
  ogType: 'website',
})

const certs = [
  {
    id: 'python',
    title: 'Python Essentials 1',
    issuer: 'Cisco Networking Academy',
    badge: '/images/pythonbadge.png',
    badgeAlt: 'Python Essentials 1 badge icon',
    certificate: '/images/pythoncertif.png',
    certificateAlt: 'Python Certificate',
  },
  {
    id: 'networking',
    title: 'Networking Basics',
    issuer: 'Cisco Networking Academy',
    badge: '/images/networking.png',
    badgeAlt: 'Networking Basics badge icon',
    certificate: '/images/networkingcert.png',
    certificateAlt: 'Networking Certificate',
  },
]

const selectedCert = ref(null)

function openCert(cert) {
  selectedCert.value = cert
}

function closeCert() {
  selectedCert.value = null
}

function onKeydown(e) {
  if (e.key === 'Escape') closeCert()
}


watch(selectedCert, (cert) => {
  document.body.classList.toggle('modal-open', !!cert)
})

onMounted(() => window.addEventListener('keydown', onKeydown))
onBeforeUnmount(() => {
  window.removeEventListener('keydown', onKeydown)
  document.body.classList.remove('modal-open')
})
</script>

<template>
  <div class="page active">
    <div class="section-title">Certifications</div>

    <div class="cert-list">
      <a
        v-for="cert in certs"
        :key="cert.id"
        class="cert-card"
        href="#"
        @click.prevent="openCert(cert)"
      >
        <div class="cert-badge">
          <img :src="cert.badge" :alt="cert.badgeAlt" class="badge-img" />
        </div>
        <div class="cert-info">
          <h3>{{ cert.title }}</h3>
          <p>{{ cert.issuer }}</p>
        </div>
      </a>
    </div>
  </div>

  <!-- Certificate modal -->
  <Teleport to="body">
    <template v-if="selectedCert">
      <div
        class="modal modal-open certificate-modal"
        tabindex="-1"
        role="dialog"
        aria-modal="true"
        @click.self="closeCert"
      >
        <div class="modal-box certificate-modal-content">
          <div class="certificate-modal-header">
            <button
              type="button"
              class="btn btn-sm btn-square certificate-modal-close"
              aria-label="Close"
              @click="closeCert"
            >
              &times;
            </button>
          </div>
          <div class="certificate-modal-body">
            <img
              :src="selectedCert.certificate"
              :alt="selectedCert.certificateAlt"
              class="certificate-modal-image"
            />
          </div>
        </div>
      </div>
    </template>
  </Teleport>
</template>