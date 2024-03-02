<template>
   <div class="ResponderModal" v-show="isVisible">
      <div class="modal-content">
        <slot></slot>
      </div>
   </div>
  </template>
  
  <script>
  export default {
   props: {
      isVisible: {
        type: Boolean,
        default: false,
      },
   },
  };
  </script>
   
<style scoped>
   
   .modal-content {
        background-color: #fefefe;
        border: 1px solid #888;

   }
   .ResponderModal{
        width: 100%;
        height: 190px;
        background-color: #FFFFFF;
        border-top: solid #DFDFDF 1px;
        padding: 12px 32px 32px 32px;
        position: fixed;
        z-index: 1000;
        bottom: 0;
        overflow: auto;
    }

    .Responder textarea{
        resize: none;
        width: 100%;
        height: 96px;
        text-align: justify;
        padding: 16px 12px;
        background-color: #E1E9F4;
        border-radius: 8px;
        border: none;
        font-size: 15px;
        font-weight: 400;
        line-height: 24px;
        letter-spacing: 0em;
        text-align: left;
        scrollbar-width: none;
        -ms-overflow-style: none; 
    }
    .Responder textarea::-webkit-scrollbar {
            display: none;
    }

    .btn-send{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: none;
        background-color: #E1E9F4;
        height: 40px;
        width: 40px;
        border-radius: 8px;
        margin-left: 8px;
    }

    .btn-send:hover{
        background-color: #e1e9f465;
    }

    .ResponderHeader, .ResponderFooter{
        display: flex;
        align-items: center;
    }

    .ResponderHeader{
        justify-content: space-between;

        margin-bottom: 16px;
    }

    .ResponderHeader p{
        width: 100%;
        font-size: 16px;
        font-weight: 500;
        line-height: 24px;
        letter-spacing: 0em;
        text-align: left;
        color: #373753;        
        border-bottom: solid 1.3px #E1E9F4;
    }

    .ResponderIcons{
        display: flex;
        gap: 14px;
        margin-left: 14px;
    }

    .ResponderIcons button{
        border: none;
        background-color: transparent;
        cursor: pointer;
    }

    .ResponderFooter{
        align-items: end;
    }
   
</style>