<script lang="ts">
export default {
  data() {
    return {
      msg: 'Welcome to Your Vue.js + TypeScript App',
      email: '',
      emailError: '',
    }
  },
  methods: {
    validateEmail(email: string):boolean {
      const re:RegExp = /\S+@\S+\.\S+/;
      return re.test(email);
    },
    submitForm() {


      if( this.email === '') {
        this.emailError = 'Whoops! It looks like you forgot to add your email';
        return;
      } 

      if (this.validateEmail(this.email)) {
        this.emailError = '';
      } 
      else {
        this.email = 'example@email/com';
        this.emailError = 'Please provide a valid email address';
        return;
      }
      console.log("submitting form")
    },
  },
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="/logo.svg" />
  </header>

  <main>
    <div class="upper">
      <h1>We are launching <strong>soon!</strong></h1>
      <p> Subscribe and get notified </p>
      <form @submit.prevent="submitForm" action="POST">
        <label for="email"></label>
        <div class="input-container">
          <input :class="{ 'border-error': emailError, 'border-normal': !emailError}" v-model="email" placeholder="Your email address..." type="text" id="email">
          <span v-if="emailError" class="input-error">{{ emailError }}</span>
        </div>
        <button type="submit">Notify Me</button>
      </form>
    </div>
    <div class="hero-container">
      <img class="hero" src="/illustration-dashboard.png" alt="hero">
    </div>
  </main>
  <footer>
    <div class="social-networks">
      <ul>
        <li><a href="#"><i class="fab fa-facebook-f"></i></a></li>
        <li><a href="#"><i class="fab fa-twitter"></i></a></li>
        <li><a href="#"><i class="fab fa-instagram"></i></a></li>
      </ul>
    </div>
    <span class="copyright">&copy; Copyright Ping. All rights reserved.</span>
  </footer>
</template>

<style scoped lang="scss">

@mixin desktop {
  @media (min-width: 768px) {
    @content;
  }
} 

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
  margin-bottom: 5rem;
}

.hero-container {
  display: flex;
  justify-content: center;

  .hero {
    width: 90%;
    margin-inline: auto;
  }
}

.upper {

  text-align: center;
  margin-bottom: 3rem;

  form {


    @include desktop {
      flex-direction: row;
    }

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    flex-direction: column;
    gap: .9rem;

    button{
      width: 90%;
      height: 2.6rem;
      border-radius: 20px;
      border: none;
      cursor: pointer;
      transition: opacity .3s ease;

      @include desktop {
        width: 40%;
      }

      &:hover {
        opacity: .6;
      }
    }
    .input-container {
      width: 100%;
      input{
        width: 90%;
        height: 2.6rem;
        border-radius: 20px;

        @include desktop {
          width: 100%;
        }
    }
  }

    input {
      padding-left: 2rem;

      &::placeholder {
        color: $gray;
        // padding-left: 1rem;
      }
    }

    .border-normal {
      border: 1px solid $pale-blue;
    }

    .border-error {
      border: 1px solid $light-red;
    }

    .input-error {
      color: $light-red;
      font-size: .8rem;
      font-weight: 400;
      text-align: center;
      font-style: italic;
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

    @include desktop {
      font-size: 3rem;
    }

    strong {
      color: $very-dark-blue;
      font-weight: 700;
    }
  }

  p {
    margin-bottom: 1rem;
  }

}

footer {

  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  margin-bottom: 2rem;

  .social-networks {
    margin-bottom: 2rem;
    ul {
      display: flex;
      list-style: none;
      padding: 0;
      gap: 2rem;
  
      li {

        &:hover {
          background-color: $blue;
          
          i {
            color: white;
          }
        }
  
        border: 1px solid $pale-blue;
        width: 2rem;
        height: 2rem;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: background-color .3s ease;

        a {
          width: 100%;
          height: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
        }
  
        i {
          color: $blue;
        }
      }
    }
  }

  span.copyright {
    color: $gray;
    font-size: .8rem;
  }
}

</style>
