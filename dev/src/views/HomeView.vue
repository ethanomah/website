<script setup>
</script>

<template>
<main>
  <div class="container-fluid info">
      <h2>I'm a 20 year old Mathematics student at <span @click="tcdLink" class="link">TCD</span>.</h2>
      <br/>
      <h2>I am currently a Data Science Intern at <span @click="tenableLink" class="link">Tenable</span>.</h2>
      <br/>
      <h2>I use <span @click="pythonLink" class="link">Python</span> and <span @click="rLink" class="link">R</span> for all things Data Science.</h2>
      <br/>
      <h2>You can find my portfolio <RouterLink to="/portfolio">here</RouterLink>.</h2>
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
      },
      pythonLink() {
        window.open('https://www.python.org/')
      },
      rLink() {
        window.open('https://www.r-project.org/')
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
    text-align: center;
    max-height: 80vh;
    padding-top: 20px;
  }

  main {
    min-height: 100%;
  }
</style>