<template>
  <login></login>
  <BBtn @click="fetchImages">Дамп картинок</BBtn>
</template>

<style>

</style>

<script>
import axios from "axios";
import login from './login/login.vue'
import BBtn from "@/components/UI/Bbtn.vue";
export default {
  name: 'LayoutDefault',

  components: {
    BBtn,
    login
  },

  methods: {
    async fetchImages() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/photos?_limit=10')
        console.log(response)
      } catch (e) {
        alert('Ошибка!')
      }
    }
  }
}
</script>