<template>
  <div class="login-form-wrapper left">
    <div class="logo-wrapper">
      <img class="logo" src="./assets/logo.svg" alt="Widitrade Logo"/>
    </div>
    <div class="login-wrapper">
      <div style="margin-bottom: 32px">
        <div class="login-label">User</div>
        <input type="text" :class="[email ? 'filling-text' : 'default-box']" class="login-input login-text"
               v-model.trim="email">
      </div>
      <div>
        <div class="login-label">Password</div>
        <div :class="[password ? 'filling-text' : 'default-box']"
             :style=" showPassword ? 'background: #fff;' : 'background: #F8F8FC;' " class="login-input"
             style="display: flex; padding: 0; margin-bottom: 48px">
          <input v-if="showPassword" type="text"
                 class="login-text" v-model="password" style="padding: 12px 0 12px 16px"/>
          <input v-if="!showPassword" :class="[password ? 'filling-text' : 'default-box']" class="login-text"
                 type="password" v-model="password" placeholder="Enter your password"
                 style="border: none; padding: 12px 0 12px 16px;">
          <img @click="toggleShow" src="../src/assets/eye.png" alt="show-password" class="show-password-icon">
        </div>
      </div>
    </div>
    <LoginButton @click="alertClick"></LoginButton>
  </div>
  <div class="right">
    <div class="img"></div>
  </div>

</template>

<script>
import LoginButton from './components/LoginButton.vue'

export default {
  name: 'App',
  components: {
    LoginButton
  },
  data: function () {
    return {
      email: null,
      password: null,
      showPassword: false
    }
  },
  methods: {
    toggleShow() {
      this.showPassword = !this.showPassword;
    },
    alertClick() {
      alert('Button clicked')
    }
  }
}
</script>

<style>

body {
  margin: 0;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.login-form-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

input:focus {
  outline: none !important;
  background: white;
}

.login-wrapper {
  width: 100%;
}

.login-label {
  font-family: 'Mulish';
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 150%;
  color: #6E7191;
  margin-bottom: 8px;
}

.logo {
  width: 115px;
  height: 82px;
}

.login-input {
  width: 100%;
  box-sizing: border-box;
  padding: 12px 16px;
  border-radius: 16px;
  justify-content: space-between;
  height: 48px;
  /*tyson.jakubowski@ya*/
}

.login-text {
  font-family: 'Inter', serif;
  font-size: 16px;
  color: #4E4B66;
}

input {
  border: none;
  width: 100%;
  padding: 0;
  border-radius: 16px;
}

.default-box {
  background: #F8F8FC;
  /* Line */
  border: 1px solid #E3E4EC;
}

.filling-text {
  border: 2px solid #4FC2C2;
  background: #fff;
}

.show-password-icon {
  width: 24px;
  height: 24px;
  align-self: center;
  justify-self: center;
  margin: 12px 16px 12px 0;
}

.right {
  display: none;
}

@media only screen and (min-width: 1201px) {
  #app {
    display: flex;
  }

  .logo-wrapper {
    align-self: flex-start;
    margin-bottom: 142px;
  }

  .left {
    width: 30%;
  }
  .right {
    width: 70%;
    display: inline;
    background-image: url("assets/photo.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
  }

  .img {
    background: linear-gradient(114.44deg, #624AF2 0%, #50DDC3 100%);
    opacity: 0.5;
    width: 100%;
    height: 100%;
  }

  .login-form-wrapper {
    height: 100vh;
    background: white;
    padding: 0 160px;
    border-radius: 32px;
  }
}

@media only screen and (min-width: 551px) and (max-width: 1200px) {
  /*Tablets [501px -> 1200px]*/
  #app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vw;
    padding: 192px 96px;
    background: #F8F8FC;
  }

  .logo-wrapper {
    align-self: center;
    margin-bottom: 142px;
  }

  .login-form-wrapper {
    background: white;
    padding: 72px;
    border-radius: 32px;
    box-shadow: 0px 8px 16px rgba(53, 55, 68, 0.04);
  }
}

@media only screen and (max-width: 550px) {
  /*Smartphones [1px -> 500px]*/
  #app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    padding: 0 32px;
  }

  .logo-wrapper {
    align-self: flex-start;
    margin-bottom: 72px;
  }
}
</style>
