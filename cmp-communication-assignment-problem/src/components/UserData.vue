<template>
  <div>
    <div>
      <input v-model="name">
      <label>enter your name</label>
    </div>
    <div>
      <input v-model="age">
      <label>enter your age</label>
    </div>
  </div>
</template>

<script>
    export default {
        name: "UserData"
    }
</script>

<style scoped>

</style>
