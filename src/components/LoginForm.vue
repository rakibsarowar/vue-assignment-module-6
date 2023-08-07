<template>
    <div class="container">
      <h2 class="mb-4">Login</h2>
      <input class="input" type="text" v-model="formData.username" placeholder="Username">
      <input class="input" type="password" v-model="formData.password" placeholder="Password">
      <button class="button" @click="login">Login</button>
    </div>
  </template>
  
  <script>
  import { defineComponent, ref, toRefs, getCurrentInstance } from 'vue';
  
  export default defineComponent({
    props: ['formData'],
    setup(props) {
      const { formData } = toRefs(props);
      const context = getCurrentInstance();
  
      const login = () => {
        context.emit('login-success');
      };
  
      return { formData, login };
    },
  });
  </script>
  