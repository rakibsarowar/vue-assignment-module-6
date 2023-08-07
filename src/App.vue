<template>
    <div id="app" class="text-center">
      <registration-form v-if="currentStep === 'registration'" :form-data="formData" @register-success="handleRegisterSuccess" />
      <login-form v-if="currentStep === 'login'" :form-data="formData" @login-success="handleLoginSuccess" />
      <success-message v-if="currentStep === 'success'" />
    </div>
  </template>
  
  <script>
  import { defineComponent, ref } from 'vue';
  import RegistrationForm from './components/RegistrationForm.vue';
  import LoginForm from './components/LoginForm.vue';
  import SuccessMessage from './components/SuccessMessage.vue';
  
  export default defineComponent({
    components: {
      RegistrationForm,
      LoginForm,
      SuccessMessage,
    },
    setup() {
      const currentStep = ref('registration');
      const formData = ref({
        username: '',
        password: '',
      });
  
      const handleRegisterSuccess = () => {
        currentStep.value = 'login';
      };
  
      const handleLoginSuccess = () => {
        currentStep.value = 'success';
      };
  
      return { currentStep, formData, handleRegisterSuccess, handleLoginSuccess };
    },
  });
  </script>
  
  <style>
  /* Add your styles here */
  </style>
  