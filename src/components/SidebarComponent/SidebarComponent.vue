<template>
   <div class="sidebar">
      <div class="sidebar-header">
        <Logo />
        <Icons/>
      </div>
      <UserIcon />
   </div>
</template>
   
<script>
import Logo from './../IconsComponents/LogoComponent.vue';
import Icons from './../IconsComponents/IconButtons.vue';
import UserIcon from './../IconsComponents/UserIcon.vue';

   export default {
    components: {
      Logo,
      Icons,
      UserIcon
    },
    data() {
       return {
         
       }
    }
   }
</script>

<style scoped>
   .sidebar{
      background-color: #FFFFFF;
      width: 64px;
      height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
   }
</style>
   