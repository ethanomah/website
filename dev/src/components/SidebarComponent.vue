<template>
  <div :class="['sidebar', { open: isOpen }]">
    <button @click="toggleSidebar" class="toggle-btn">☰</button>
    <ul>
      <li><a href="#">Home</a></li>
      <!-- <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li> -->
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },
  mounted() {
  },
  methods: {
    toggleSidebar() {
      this.isOpen = !this.isOpen;
    },
  }
}
</script>

<style scoped>
.sidebar {
  position: fixed;
  left: -300px;
  top: 0;
  width: 300px;
  height: 100%;
  background-color: var(--color-background);
  color: white;
  transition: left 0.3s ease;
  padding-top: 60px;
  z-index: 1000;
}

.sidebar.open {
  left:0;
}

.sidebar ul {
  list-style: none;
  padding: 0;
}

.sidebar ul li {
  padding: 15px 20px;
}

.sidebar ul li a {
  color: white;
  text-decoration: none;
}

.sidebar .toggle-btn {
  font-size: 24px;
  color: white;
  background: none;
  border: none;
  cursor: pointer;
  position: absolute;
  top: 10px;
  right: -50px; /* Initially place the button outside the sidebar */
}

.sidebar.open .toggle-btn {
  right: 10px; /* Move the button inside the sidebar when open */
  transition: left 0.3s ease;
}

@media (min-width: 1024px) {
}

</style>
