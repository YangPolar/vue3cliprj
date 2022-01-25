<template>
  <div>
    <input v-model="title" />
    <hr />
    <div v-if="isVisible" class = "box"></div>
    <div v-else-if="isVisible2" class = "box two"></div>
    <div v-else class = "box three"></div>
    <button @click="toggleBox">Toggle Box</button>
    <hr />
    <LoginForm msg="Hello Vue 3!"/>
  </div>
</template>

<script>
// @ is an alias to /src
import LoginForm from '@/components/LoginForm.vue'

import '@/assets/styles/register.css'

export default {
  name: 'Register',
  data () {
    return {
      title: 'Login Form',
      isVisible: false,
      isVisible2: true
    }
  },
  methods: {
    toggleBox: function () {
      this.isVisible = !this.isVisible
    }
  },
  components: {
    LoginForm
  }
}
</script>
