<template>
  <div >
    <H1>Register</H1>

    <input v-model="email" type="email" name="email" placeholder="Email">
    <br>
    <input v-model="password" type="password" name="password" placeholder="Password">
    <br>
     <button @click="register">Register</button>

  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
