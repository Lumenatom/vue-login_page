<template>
  <div class="container" id="app">
    <div class="alertBaner">
      <div ref="loginAlert" class="alert alert-danger loginAlert" role="alert">
        Invalid login
      </div>
      <div ref="passwordAlert" class="alert alert-danger" role="alert">
        Invalid password
      </div>
      <div ref="codeAlert" class="alert alert-danger" role="alert">
        Incorrect code
      </div>
      <div ref="complitedAlert" class="alert alert-success" role="alert">
        Complited!
      </div>
    </div>
    <div class="container" id="formLogin">
      <div class="login">
        <input ref="loginInput" type="email" class="form-control" placeholder="login">
      </div>
      <div class="password">
        <input ref="passwordInput" type="password" class="form-control" placeholder="password">
      </div>
      <div class="numberCheck" ref="securetyCode">
        <input ref="codeInput" type="number" class="form-control" placeholder="code">
      </div>
      <div>
        <button v-on:click="loginCheck" class="btn btn-primary">LOGIN</button>
      </div>

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
      const loginInput = this.$refs.loginInput.value;
      const passwordInput = this.$refs.passwordInput.value;
      const codeInput = this.$refs.codeInput.value;
      if (loginInput === 'admin') {
        // console.log(11111);
      } else {
        this.$refs.loginAlert.classList.add('active');
        setTimeout(() => {
          this.$refs.loginAlert.classList.remove('active');
        }, 3000)
      }
      if (passwordInput === 'admin') {
        // console.log(11111);
      } else {
        this.$refs.passwordAlert.classList.add('active');
        setTimeout(() => {
          this.$refs.passwordAlert.classList.remove('active');
        }, 3000)
      }
      if (loginInput && passwordInput) {
        this.$refs.securetyCode.classList.add('active');
        if (codeInput === "1111" && loginInput && passwordInput) {
          this.$refs.complitedAlert.classList.add('active');
          setTimeout(() => {
            this.$refs.complitedAlert.classList.remove('active');
          }, 3000)
        } else {
          this.$refs.codeAlert.classList.add('active');
          setTimeout(() => {
            this.$refs.codeAlert.classList.remove('active');
          }, 3000)
        }
      }



    }

  }
}



</script>

<style>
body {
  background: #2C3E50;
  padding: 0 10px;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 540px;
  background-color: #fff;
  padding: 50px;
  border-radius: 20px;
  margin-top: 60px;



}

#formLogin {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.numberCheck {
  display: none;
}

.alert {
  width: 375px;
  /* color: #fff;
  background-color: rgba(255, 68, 0, 0.81); */
  display: none;
}

.alertBaner {
  position: absolute;
  bottom: 0;
  right: 0;
  margin: 10px;
}

.active {
  display: block;
}


@media (max-width:575px) {
  .alert {
    width: 100%;

  }

  .alertBaner {
    width: 100%;
    padding: 10px;
    margin: 0;
  }
}
</style>
