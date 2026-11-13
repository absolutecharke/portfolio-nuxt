<script setup>
const profilePhoto = '/images/dsadds.jpg'

useSeoMeta({
  title: 'Home - Charles Pineda | IT Portfolio',
  description: 'Portfolio of Charles Pineda, a passionate 2nd year IT student with a strong foundation in web development and software engineering.',
  ogTitle: 'Charles Pineda - BSIT Portfolio',
  ogDescription: 'Explore the portfolio and short intro of Charles Pineda, a 2nd year IT student specializing in web development.',
  ogImage: profilePhoto,
  ogType: 'profile',
})
</script>

<template>
  <div class="page active">
    <div class="profile-header">
      <div class="profile-sidebar">
        <div class="photo-box">
          <img :src="profilePhoto" alt="Profile photo" />
        </div>
        <div class="name-pill">
          <h1>Charles Pineda</h1>
        </div>
      </div>

      <div class="right-column">
        <div class="card portfolio-card other-pill">
          <div class="card-body portfolio-card-body">
            <div class="label">Other Info</div>
            <p>BSIT Undergraduate · Bacoor, Cavite, PH</p>
          </div>
        </div>

        <div class="card portfolio-card intro-box">
          <div class="card-body portfolio-card-body">
            <h2>Short Intro</h2>
            <p>
              A passionate and dedicated 2nd year IT student with a great interest
              in web development and software engineering with a solid foundation
              in programming.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>