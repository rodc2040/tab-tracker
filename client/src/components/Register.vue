<template>
  <div class="register">
   <h1>Register</h1>
   <div>
    <input
        v-bind="email"
        type="email"
        name="email"
        placeholder="Enter your email">
  </div>

  <div>
    <input
      v-bind="password"
      type="password"
      name="password"
      placeholder="Enter your password">
    </div>
    <div>
    <button
    @click="register">
    Register
    </button>
  </div>
  </div>
</template>

<script>
import AuthenticationServices from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationServices.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
