<script>

export default {
  data() {
    return {
      host: "http://xxxxxx-m2.domain.ru/login",
      login: "",
      password: "",
      error: ""
    }
  },
  methods: {
    async postauth() {
      const res = await fetch('http://xxxxxx-m2.domain.ru/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },

        credentials: 'include',
        body: JSON.stringify({
          login: 'sdsadsad',
          password: 'dsadsadsad'
        })
      })
      console.log(res)
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <form @submit.prevent>
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