<script>
import BBtn from "@/components/UI/Bbtn.vue";
export default {
  name: 'B-input',
  components: {BBtn},
  props: {
    modelValue: [String, Number]
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<template>
  <input
      :value="modelValue"
      @input="updateInput"
      class="input"
      type="text"
  >
</template>

<style scoped>
  .input {
    background: none;
    border: darkorange 2px solid;
    border-radius: 2px;
    padding: 10px;
    font-size: 20px;
    color: darkorange;
    margin: 5px;
  }
</style>