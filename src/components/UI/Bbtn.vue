<script>
export default {
  name: 'B-btn'
}
</script>

<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<style scoped>
  .btn {
    background: none;
    border: darkorange 2px solid;
    border-radius: 2px;
    padding: 10px;
    font-size: 20px;
    color: darkorange;
    cursor: pointer;
    margin: 5px;
  }

  .btn:hover {
    transform: scale(1.1);
    transition: all ease .4s;
  }
</style>