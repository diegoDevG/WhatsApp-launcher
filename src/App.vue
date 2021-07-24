<template>
<div class="app-wrapper">
  <WhatsappForm />
  <MainFooter />
</div>
</template>

<script>
import WhatsappForm from './components/WhatsappForm.vue';
import MainFooter from './components/MainFooter.vue';

export default {
  name: 'App',
  components: {
    WhatsappForm,
    MainFooter,
  },
};
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */
  /* margin-top: 60px; */
}

.app-wrapper{
  height:100vh;
  display: flex;
  justify-content:center;
  align-items:center;
  flex-direction:column;
}

@media (max-width: 768px) {
  .app-wrapper {
    height: auto;
    padding-bottom: 3rem;
    padding-top: 3rem;
   }
  }

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type=number] {
  -moz-appearance: textfield;
}
</style>
