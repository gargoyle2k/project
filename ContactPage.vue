// ContactPage.vue
<template>
  <div>
    <h1>Contact Us</h1>
    <form @submit.prevent="submitForm">
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="name" required>
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="email" required>
      <label for="message">Message:</label>
      <textarea id="message" v-model="message" required></textarea>
      <button type="submit">Send</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      name: '',
      email: '',
      message: '',
    }
  },
  methods: {
    submitForm() {
      axios.post('/api/contact', {
        name: this.name,
        email: this.email,
        message: this.message,
      }).then(response => {
        console.log('Form submitted successfully!')
      }).catch(error => {
        console.error('Error submitting form:', error)
      })
    },
  },
}
</script>