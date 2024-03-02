<template>
  <div id="app">
    <VueSidebar/>  
    <ChatComponentVue/>
  </div>

</template>

<script>
import ChatComponentVue from './components/ChatComponent/ChatComponent.vue';
import VueSidebar from './components/SidebarComponent/SidebarComponent.vue';

export default {
  name: 'App',
  components: {
    ChatComponentVue,
    VueSidebar
}
}
</script>

<style>
  @font-face {
      font-family: 'Cerebri Sans Pro';
      src: url('./assets/Cerebri.Sans.Pro/CerebriSansPro-Regular.ttf') format('truetype');
      font-weight: normal;
      font-style: normal;
  }


  *{
      font-family: 'Cerebri Sans Pro', 'Montserrat', sans-serif;
      padding: 0; 
      margin: 0;
      box-sizing: border-box;
  }

  #app{
    display: flex;
    width: 100%;

  }
</style>
