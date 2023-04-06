<script lang="ts">
  export default {
    data() {
      return {
        msg: 'Welcome to Your Vue.js + TypeScript App'
      }
    }
  }

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="/logo.svg" width="125" height="125" />
  </header>

  <main>
    <div class="form-container">

    </div>
    <div class="hero-container">
      <img class="hero" src="/illustration-dashboard.png" alt="hero">
    </div>
  </main>
</template>

<style scoped lang="scss">



header {

  text-align: center;

  img {
    width: 80px;
    height: 30px;
  }
}

.hero-container{
  display: flex;
  justify-content: center;
  .hero {
    width: 90%;
    margin-inline: auto;
  }
}

</style>
