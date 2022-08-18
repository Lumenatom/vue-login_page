<template>
  <div class="container-sm" id="app">
    <div class="login">
      <input type="email" class="form-control" placeholder="login">
    </div>
    <div class="password">
      <input type="password" class="form-control" placeholder="password">
    </div>
    <div class="numberCheck" ref="securetyCode">
      <input type="number" class="form-control" placeholder="code">
    </div>
    <div>
      <button v-on:click="loginCheck" class="btn btn-primary">LOGIN</button>
    </div>
  </div>
</template>




<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
export default {

  name: 'App',
  components: {
  },
  methods: {
    loginCheck: function () {

      this.$refs.securetyCode.classList.toggle('active');

    }
  }
}



</script>

<style>
body {
  background: #2C3E50;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 540px;
  background-color: #fff;
  padding: 50px;
  border-radius: 20px;

}

.login {}

.active {
  display: none;
}
</style>
