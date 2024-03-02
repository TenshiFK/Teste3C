<template>
  <div>
     <div class="btn-tabs">
       <button
         class="tab"
         v-for="(tab, index) in tabs"
         :key="index"
         @click="selectTab(index)"
         :class="{ 'active-tab': selectedTab === index, 'disabled': tab.disabled }"
         :disabled="tab.disabled"
       >
         {{ tab.title }}
         <div class="avisoNumItens">
          {{ tab.numItens }}
         </div>
       </button>
       <button class="btn-menu">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="#677c92" d="M7 12a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0"/></svg>     
      </button>
    </div>
     <div
       class="tab-content"
       v-for="(tab, index) in tabs"
       :key="index"
       v-show="selectedTab === index"
     >
       <slot :name="'tab-content-' + index"></slot>
     </div>
  </div>
 </template>

<script>
export default {
 data() {
    return {
      tabs: [
      { title: 'Conversas', content: '', disabled: false, numItens: 16 },
      { title: 'Grupos', content: '', disabled: true, numItens: 4 },
      { title: 'Fila', content: '', disabled: true, numItens: 25 },
      ],
      selectedTab: 0, // Aba selecionada por padrão
    };
 },
 methods: {
    selectTab(index) {
      this.selectedTab = index;
    },
 },
};
</script>

<style scoped>
    .btn-tabs{
      width: 100%;
      display: flex;
      align-items:end;
    }
    .tab {
      cursor: pointer;
      padding: 4px;
      border: none;
      background-color: transparent;
      font-size: 14px;
      line-height: 16px;
      color: #373753;
      text-align: center;
      display: inline-flex;
      gap: 8px;
    }

    .tab:first-child {
        margin-left: 20px;
        margin-right: 13px;
      }
    .tab:nth-child(2){
      margin-right: 16px;
    }

    .tab:nth-child(3){
      margin-right: 8px;
    }

    .btn-tabs{
      width: 100%;
      border-bottom: 1px solid #ddd; /* Linha base cinza */

    }

    .tab-content {
        width: 100%;
        border-top: none;
    }

    .active-tab {
        border-bottom: solid 2px #3057f2;
        color: #3057F2;
        font-weight: 500;
        z-index: 2; /* Garante que a linha ativa apareça sobre a linha base */
    }

    .tab.disabled {
      color: #373753;
      cursor: default;
      opacity: 0.6;
    }

    .btn-menu{
      border: none;
      background: transparent;
      padding: 0;
      cursor: pointer;
    }

    .avisoNumItens{
      background-color: #E1E9F4;
      color: #283E5D;
      font-size: 12px;
      width: 18px;
      height: 18px;
      border-radius: 50%;
      padding: 8px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
</style>