<template>
    <div class="icons-sidebar">
       <button><img class="icon-phone-sidebar" src="./../../assets/phone.png" alt="Phone" /></button>
       <button><img class="icon-whats-sidebar" src="./../../assets/whatsapp.png" alt="WhatsApp" /></button>
    </div>
</template>
<style scoped>
   .icons-sidebar{
      margin: 45px 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      gap: 24px;
   }
   button{
      border: none;
      background-color: transparent;
      cursor: pointer;
   }
   .icon-phone-sidebar:hover, .icon-whats-sidebar:hover{
      width: 20px;
   }
</style>