<template>
  <div>
    <div class="container">
      <div class="img-section"></div>
      <div class="form-section">
        <div class="form text-block">
          <h1>Заходи</h1>
          <!-- <p><input type="text" placeholder="Логин" /></p> -->
          <p><animated-input placeholder="Логин" /></p>
          <p><animated-input type="password" placeholder="Пароль" /></p>
          <br />
          <hr />
          <p class="login-button-p">
            <button class="login-button">Войти</button>
          </p>
          <p>Если у вас возникли проблемы со входом, cожалею.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import AnimatedInput from "../components/AnimatedInput.vue";
  export default {
    components: {
      AnimatedInput,
    },
  };
</script>

<style scoped>
  .img-section {
    /* background-color: #edecfa; */
    /* background: rgb(237, 236, 250); */
    background-image: url(https://forums.goha.ru/cdn/forum/picture/110/110212.picture),
      linear-gradient(
        0deg,
        rgba(237, 236, 250, 1) 0%,
        rgba(255, 255, 255, 1) 100%
      );
    background-size: cover;
    background-position: center;
  }

  .container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    height: 100vh;
  }

  .form-section {
    padding: 70px;
    position: relative;
  }

  .form {
    display: flex;
    flex-direction: column;
    max-width: 400px;
    margin: 0 auto;
    height: 100%;
    width: 100%;
  }

  .form p:last-child {
    margin-top: auto;
    color: #ddd;
  }

  .login-button {
    width: 100%;
    color: white;
    background-color: black;
  }

  .login-button-p {
    /* margin-top: auto; */
  }

  input[type="password"] {
    border: none !important;
  }

  @media screen and (max-width: 750px) {
    .img-section {
      display: none;
    }

    .form {
      max-width: 100%;
    }

    .form-section {
      max-width: 400px;
      margin: 0 auto;
      padding: 25px;
      height: 100%;
    }

    .container {
      display: block;
    }
  }
</style>
