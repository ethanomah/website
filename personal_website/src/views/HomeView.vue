<script setup>
</script>

<template>
<main>
  <div class="container-fluid" style="align: center; text-align: center;">
    <div class="info">
      <h2>I'm a 20 year old Mathematics student at <span @click="tcdLink" class="link">TCD</span>.</h2>
    </div>
    <div class="info">
      <h2>I am currently a Data Science Intern at <span @click="tenableLink" class="link">Tenable</span>.</h2>
    </div>
  </div>
</main>
</template>

<script>
  export default {
    methods: {
      tcdLink() {
        window.open('https://www.tcd.ie/')
      },
      tenableLink() {
        window.open('https://www.tenable.com/')
      }
    }
  }
</script>

<style>
  .link {
    cursor: pointer;
    color: rgba(0, 208, 255, 0.575);
  }

  .info{
    padding: 20px;
  }
</style>