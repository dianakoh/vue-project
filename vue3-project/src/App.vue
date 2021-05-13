<template>
  <div class="name">{{ name }}</div>
</template>

<script>
export default {
  setup() {
    const name = 'Dev Flowing';

    return  {
      name
    };
  },
}
</script>

<style scoped>
  .name {
    color: red;
  }
</style>