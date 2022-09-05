<template>
  <div class="home">
    <h1>Hello This is Vue Application</h1>
    <p>Made by parkjg20</p>
  </div>
</template>

<script>
export default {
  name: 'PageHome',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.home {
  flex-direction: column;
}

</style>
