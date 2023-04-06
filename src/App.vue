<script lang="ts">
  export default {
    data() {
      return {
        msg: 'Welcome to Your Vue.js + TypeScript App',
        email: '',
      }
    }
  }

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="/logo.svg"/>
  </header>

  <main>
    <div class="upper">
      <h1>We are launching <strong>soon!</strong></h1>
      <p> Subscribe and get notified </p>
      <form action="POST">
        <label for="email"></label>
        <input placeholder="Your email address..." type="text" id="email">
        <button type="submit">Notify Me</button>
      </form>
    </div>
    <div class="hero-container">
      <img class="hero" src="/illustration-dashboard.png" alt="hero">
    </div>
  </main>
</template>

<style scoped lang="scss">
// Colors

// Primary

$blue: hsl(223, 87%, 63%);

// Secondary

$pale-blue: hsl(223, 100%, 88%);
$light-red: hsl(354, 100%, 66%);

// Neutral

$gray: hsl(0, 0%, 59%);
$very-dark-blue: hsl(209, 33%, 12%);


header {

  text-align: center;

  img {
    width: 80px;
    height: 25px;
  }
  margin-bottom: 2rem;
}

main {
  padding: 0 1rem;
}

.hero-container{
  display: flex;
  justify-content: center;
  .hero {
    width: 90%;
    margin-inline: auto;
  }
}

.upper{

  text-align: center;
  margin-bottom: 3rem;

  form {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-direction: column;
    gap: .9rem;

    button,input {
      width: 90%;
      height: 2.6rem;
      border-radius: 20px;
      border: 1px solid $pale-blue;
    }
    input {
      padding-left: 1rem;

      &::placeholder {
        color: $gray;
        padding-left: 1rem;
      }
    }

    button {
      background-color: $blue;
      color: white;
      border: none;
      font-weight: 600;
    }
  }

  h1 {
    font-size: 1.5rem;
    font-weight: 300;
    margin-bottom: 1rem;
    color: $gray;
    line-height: 40px;

    strong {
      color: $very-dark-blue;
      font-weight: 700;
    }
  }

  p {
    margin-bottom: 1rem;
  }

}

</style>
