<template>
  <button @click="onClick" class="login-btn">
    <slot>Login</slot>
  </button>
</template>

<script>
export default {
  name: 'LoginButton',
  props: {
    onClick: {
      type: Function,
      required: true
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.login-btn {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 14px 42px;
  background: #22A2A2;
  border-radius: 60px;
  width: 100%;

  font-family: 'Inter';
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 150%;
  /* identical to box height, or 24px */


  color: #FFFFFF;
  border: none;
}
</style>
