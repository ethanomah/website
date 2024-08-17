<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <canvas style="position: absolute; left:0; top:0; z-index:-1; width: 100%; height: 100%; opacity: 0.4;">
  </canvas>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->
    <div class="container-fluid" style="align: center; text-align: center; align-items: center;">

      <h1 id="demo"></h1>
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <!-- <RouterLink to="/portfolio">Portfolio</RouterLink> -->
        <!-- <RouterLink to="/contact">Contact</RouterLink> -->
      </nav>
    </div>
  </header>
  <body class="test">
    <!-- <div id="bgAnimation" style="position: fixed; z-index: -1;"></div> -->
    <RouterView style="z-index:1"/>
  </body>
  <footer>
    <div class="badge-base LI-profile-badge" data-locale="en_US" data-size="medium" data-theme="dark" data-type="VERTICAL" data-vanity="ethan-o-mahony" data-version="v1"><a class="badge-base__link LI-simple-link" href="https://ie.linkedin.com/in/ethan-o-mahony?trk=profile-badge"></a></div>
  </footer>

</template>

<script>
export default {
  data() {
    return {
      i: 0,
      txt : '{ethan o\'mahony}',
      speed : 125
    }
  },
  mounted() {
    this.typeWriter();
  },
  methods: {
    async typeWriter() {
      if (this.i < this.txt.length) {
        document.getElementById("demo").innerHTML += this.txt.charAt(this.i);
        this.i++;
        setTimeout(this.typeWriter, this.speed);
      }
    }
  }
}
</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  text-align: start;
  /* width: 100%;
  margin: 0 auto; */
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 18px;
  text-align: center;
  margin-top: 2rem;
}

.test{
    background: none;
    background-color: transparent;
    background-image: none;
  }

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    justify-content: center;
    place-items: center;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: center;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
