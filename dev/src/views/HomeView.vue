<script setup>
import gsap from 'gsap';
</script>

<template>
  <!-- <main> -->
    <div class="container-fluid info">
      <TransitionGroup 
        appear
        name="slide-fade"
        @before-enter="onBeforeEnter"
        @enter="onEnter"
      >
        <h2 key="sentence1" data-index="1" class="sentence">I'm a <span class="age">{{age.toFixed(12)}}</span> year old Associate Data Scientist at <span @click="tenableLink" class="link">Tenable</span>.</h2> 
        <h2 key="sentence2" data-index="2" class="sentence">In 2023 I graduated from <span @click="tcdLink" class="link">Trinity College Dublin</span> with a B.A. in Mathematics and a Minor in Statistics.</h2>
        <h2 key="sentence3" data-index="3" class="sentence">I use <span style="color: rgba(0, 208, 255, 0.575);">Python</span> and <span style="color: rgba(0, 208, 255, 0.575);">SQL</span> for all things Data Science.</h2>
        <!-- <h2 key="sentence4" data-index="4" class="sentence">You can find my portfolio <RouterLink to="/portfolio">here</RouterLink>.</h2> -->
      </TransitionGroup>
    </div>
  <!-- </main> -->
</template>

<script>
  export default {
    data() {
      return {
        age: 0
      }
    },
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
      },
      currentAge() {
          var bday = new Date("2001-07-27");
          var today = new Date();
          var diff = today - bday;
          this.age = diff / (1000 * 60 * 60 * 24 * 365.25);
      },
      onEnter(el, done) {
        gsap.to(el, {
          opacity: 1,
          delay: el.dataset.index * 0.3,
          onComplete: done
        })
      },
      onBeforeEnter(el) {
        el.style.opacity = 0
      },
    },
    mounted() {
      this.currentAge();
      setInterval(this.currentAge, 50);
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
    /* max-height: 80vh; */
    padding-top: 20px;
  }

  .age {
    color: rgba(0, 208, 255, 0.575);
  }

  .sentence {
    line-height: 50px;
    padding-top:2vh;
    padding-bottom:2vh;
  }

  main {
    padding-bottom:20vh;
    /* min-height: 100%; */
  }
</style>