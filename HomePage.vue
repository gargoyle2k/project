// HomePage.vue

<template>
  <div>
    <h1>Welcome to our website!</h1>
    <p v-if="data.length === 0">Loading...</p>
    <ul v-else>
      <li v-for="item in data" :key="item.id">{{ item.name }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      data: [],
    }
  },
  mounted() {
    axios.get('/api/items').then(response => {
      this.data = response.data
    })
  },
}
</script>