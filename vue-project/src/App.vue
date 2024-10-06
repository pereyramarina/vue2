<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav>
    <RouterLink to="/"></RouterLink>
  </nav>
  <header>
    <div class="wrapper"></div>
  </header>

  <RouterView />
  <div class="wrapper">
    <form @submit.prevent="submitForm" id="loginForm">
      <h1>Login</h1>

      <div class="input-bx">
        <input v-model="user" name="user" type="text" placeholder="Usuario" required />
        <ion-icon class="icon" name="person-circle"></ion-icon>
      </div>

      <div class="input-bx">
        <input
          v-model="password"
          name="password"
          type="password"
          placeholder="Contraseña"
          required
        />
        <ion-icon class="icon" name="lock-closed"></ion-icon>
      </div>

      <div class="remember-forgot">
        <label><input v-model="remember" type="checkbox" name="remember" /> Recordarme</label>
        <a href="#">Olvidaste tu contraseña</a>
      </div>

      <button type="submit" class="btn">Ingresar</button>
    </form>
  </div>
</template>

<style scoped>
/* estilos generales */
@import url('https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,300..900;1,300..900&family=Saira:ital,wght@0,100..900;1,100..900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Saira', sans-serif;
  font-size: 16px;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  background: url('../public/background.jpg');
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  max-height: 100vh;
  max-width: 100vw;
}

/* estilos del componente */

.wrapper {
  width: 400px;
  background: transparent;
  border: 2px solid rgba(12, 4, 4, 0.2);
  backdrop-filter: blur(20px);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  color: #0d0000;
  padding: 30px 40px;
  border-radius: 15px;
}

.wrapper h1 {
  font-size: 3em;
  text-align: center;
}

.wrapper .input-bx {
  position: relative;
  width: 100%;
  height: 50px;
  margin: 30px 0;
}

.wrapper .input-bx input {
  width: 100%;
  height: 100%;
  background: transparent;
  border: none;
  outline: none;
  border: 2px solid rgba(0, 0, 0, 0.2);
  border-radius: 15px;
  color: #000000;
  padding: 20px 45px 20px 20px;
}

.wrapper .input-bx input::placeholder {
  color: #060000;
}

.wrapper .input-bx .icon {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1.5em;
}

.wrapper .remember-forgot {
  display: flex;
  justify-content: space-between;
  font-size: 1.2em;
  margin: -15px 0 15px;
}

.wrapper .remember-forgot label input {
  accent-color: #000000;
  margin-right: 3px;
}

.wrapper .remember-forgot a {
  color: #010000;
  text-decoration: none;
}

.wrapper .remember-forgot a:hover {
  text-decoration: underline;
}

.wrapper button {
  width: 100%;
  height: 50px;
  border-radius: 15px;
  border: none;
  outline: none;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  font-size: 1.2em;
  font-weight: 600;
  color: #010000;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
