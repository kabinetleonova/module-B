<script>

import BBtn from "@/components/UI/Bbtn.vue";
import BInput from "@/components/UI/Binput.vue";

export default {
  components: {BInput, BBtn},
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
      <BInput v-model="login" placeholder="Логин"></BInput>
      <BInput v-model="password" placeholder="Пароль"></BInput>
      <BBtn @click="postauth">Войти</BBtn>
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