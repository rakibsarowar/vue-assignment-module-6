<template>
    <div class="container">
      <h2 class="mb-4">Register</h2>
      <input class="input" type="text" v-model="formData.name" placeholder="Name">
      <input class="input" type="text" v-model="formData.username" placeholder="Username">
      <input class="input" type="password" v-model="formData.password" placeholder="Password">
      <button class="button" @click="register">Register</button>
    </div>
  </template>
  
  <script>
  import { defineComponent, ref, toRefs, getCurrentInstance } from 'vue';
  
  export default defineComponent({
    props: ['formData'],
    setup(props) {
      const { formData } = toRefs(props);
      const context = getCurrentInstance();
  
      const register = () => {
        context.emit('register-success');
      };
  
      return { formData, register };
    },
  });
  </script>
  