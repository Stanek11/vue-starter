<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="loggedin">Zalogowany  {{email}}
      <a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
    <input type="email" v-model="email">
      <button @click="logMeIn()">Zaloguj się</button>
    <div v-if="!email.includes('@')">Twój mail jest nieprawidłowy</div>
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

    </div>
  </div>
</template>

<script>

import "milligram";
export default {
data() {
  return {
    email: 'patryk.stankiewicz@gmail.com',
    loggedin: false,
    password: ''
  };
},
  methods: {
  logMeIn() {
    this.loggedin = true;
  },
    logMeOut() {
      this.loggedin = false;
    },
  }
}

</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
