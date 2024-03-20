<script>
import axios from "axios"

export default {
  data() {
    return {
      login: "",
      password: "",
      error: ""
    }
  },
  methods: {
    postauth() {
      if(this.login.trim().length < 3) {
        this.error = "Логин должен быть более чем из 3 символов"
      }

      if(this.password.trim().length < 8) {
        this.error = "Логин должен быть более чем из 3 символов"
      }

      this.error = ""

      axios.post()
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <form>
      <input v-model="login" placeholder="Логин">
      <input v-model="password" placeholder="Пароль">
      <button @click="postauth">Войти</button>
    </form>

    <p>{{ error }}</p>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
}
</style>