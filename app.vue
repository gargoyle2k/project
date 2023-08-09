// App.vue
<template>
  <div>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/contact">Contact</router-link>
    <router-view></router-view>
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'
import AboutPage from './components/AboutPage.vue'
import ContactPage from './components/ContactPage.vue'

export default {
  components: {
    HomePage,
    AboutPage,
    ContactPage,
  },
}
</script>