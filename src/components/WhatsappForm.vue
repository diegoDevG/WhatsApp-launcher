<template>
<!-- eslint-disable max-len -->
<div class="container">
  <div class="px-5 lg:w-1/2  mx-auto flex flex-wrap">
    <div style='background: #00776b' class="md:w-1/2 w-full p-5 flex justify-center align-center flex-col text-white  rounded-t-lg md:rounded-l-lg md:rounded-r-none">
      <h2 class="text-gray-200 text-lg mb-1 font-medium title-font">WhatsApp Launcher</h2>
      <img src="https://web.whatsapp.com/img/intro-connection-dark_0ee01153183b5ebd9b296399cc2104b0.jpg" width="75" class="rounded-full m-auto mt-8 mb-4"/>
          <p class="leading-relaxed mb-5 text-gray-200">Inicia un chat de WhatsApp con números que no estan en tus contactos.</p>
    </div>
    <div style="background-color: #d8ded7" class=" bg-form-pattern rounded-t-none rounded-b-lg md:rounded-l-none md:rounded-r-lg p-8 flex flex-col  md:w-1/2  md:ml-auto w-full md:mt-0 relative z-10 shadow-md">
      <div class="relative mb-4">
        <input required type="number" id="number" name="number" placeholder="Numero" v-model="number" class="w-full bg-white rounded border border-gray-300 focus:border-green-500 focus:ring-2 focus:ring-green-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
      </div>
      <div class="relative mb-4">
        <textarea id="message" name="message" placeholder="Mensaje..." v-model="message" class="w-full bg-white rounded border border-gray-300 focus:border-green-500 focus:ring-2 focus:ring-green-200 h-32 text-base outline-none text-gray-700 py-1 px-3 resize-none leading-6 transition-colors duration-200 ease-in-out"></textarea>
      </div>
      <a v-if='hasAValidNumber' :href="`https://api.whatsapp.com/send/?phone=57${number}&text=${message}&app_absent=0`" class="text-white bg-green-500 border-0 py-2 px-6 focus:outline-none hover:bg-green-600 rounded text-lg text-center" >
        <button class="flex items-center mx-auto" >
          Continuar al chat
          <svg xmlns="http://www.w3.org/2000/svg" width="21px" class="h-5 w-5 transform rotate-90 ml-2" viewBox="0 0 20 20" fill="currentColor">
            <path d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 001.169 1.409l5-1.429A1 1 0 009 15.571V11a1 1 0 112 0v4.571a1 1 0 00.725.962l5 1.428a1 1 0 001.17-1.408l-7-14z" />
          </svg>
        </button>
      </a>

        <button v-else class="text-white flex items-center mx-auto justify-center w-full bg-gray-500 border-0 py-2 px-6 focus:outline-none  rounded text-lg text-center cursor-not-allowed" >
          Continuar al chat
          <svg xmlns="http://www.w3.org/2000/svg" width="21px" class="h-5 w-5 transform rotate-90 ml-2" viewBox="0 0 20 20" fill="currentColor">
            <path d="M10.894 2.553a1 1 0 00-1.788 0l-7 14a1 1 0 001.169 1.409l5-1.429A1 1 0 009 15.571V11a1 1 0 112 0v4.571a1 1 0 00.725.962l5 1.428a1 1 0 001.17-1.408l-7-14z" />
          </svg>
        </button>
      <p class="text-xs text-gray-800  mt-3">Al hacer click en el boton seras redirigido a la aplicacion de WhatsApp instalada en tu dispositivo</p>

    </div>
  </div>
</div>

</template>

<script>

export default {
  data() {
    return {
      number: '',
      message: '',
    };
  },
  computed: {
    hasAValidNumber() {
      return this.number.length === 10;
    },
  },
};

</script>

<style >

body{
  background: url(./../assets/weaves.svg);
  background-repeat: no-repeat;
  background-position: bottom;
  height:100%;
}

.container{
  flex: 1 0 auto;
  display: flex;
  align-items: center;
}

</style>
