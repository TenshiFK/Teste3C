<template>
    <div class="chat-component-areaContatos">

        <div class="chat-component-header">
        Omnichannel 3C+ 
        <div class="line-header"/>
        </div>
        <div class="chat-component-pesquisa">
        <form>
            <button class="btn-Pesquisa">
            <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24"><path fill="#677c92" d="m19.485 20.154l-6.262-6.262q-.75.639-1.725.989q-.975.35-1.96.35q-2.402 0-4.066-1.663q-1.664-1.664-1.664-4.065T5.47 5.436q1.663-1.667 4.064-1.667q2.402 0 4.068 1.664q1.666 1.664 1.666 4.067q0 1.042-.369 2.017q-.37.975-.97 1.668l6.262 6.261zM9.538 14.23q1.99 0 3.361-1.37q1.37-1.37 1.37-3.361q0-1.99-1.37-3.36q-1.37-1.37-3.36-1.37q-1.99 0-3.361 1.37q-1.37 1.37-1.37 3.36q0 1.99 1.37 3.36q1.37 1.37 3.36 1.37"/></svg>
            </button>
            <input type="text" placeholder="Pesquisar">
        </form>
        <div>
            <button class="chat-component-pesquisa-icon"><svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"><path fill="white" d="M21 13h-8v8h-2v-8H3v-2h8V3h2v8h8z"/></svg></button>
        </div>
        </div>

        <TabComponent>
          <template #tab-content-0>
            <div class="lista-contatos">
              <div
                  v-for="contato in contatos"
                  :key="contato.id"
                  @click="selecionarContato(contato.id)"
                  :class="{ ativo: contatoAtual && contatoAtual.id === contato.id }"
              > 
              <div class="area-contato">
                  <div class="area-contato-left">
                  <img :src='contato.imgPerfil' width="40" height="40" alt=""> 
                  <div class="area-contato-left-texto">
                      <p>{{ contato.nome }}</p>
                      <span>{{ contato.textoUltimaConversa }}</span>
                  </div>
                  </div>
                  <div class="area-contato-right">
                  <p>{{ contato.dataUltimaConversa }}</p>

                  <div v-if="contato.mnsNLidas !== 0">{{ contato.mnsNLidas }}</div>
                  </div>
              </div>
              </div>
            </div>
          </template>
        </TabComponent>


    </div>
</template>
   
<script>
    import TabComponent from './../../TabComponent/TabComponent.vue';

   export default {
    props: ['contatos', 'selecionarContato', 'contatoAtual'],
    components: {
    TabComponent
    },
   };
</script>

<style socped>
    .chat-component-header{
      padding: 15px 11px 15px 24px;
      font-size: 16px;
      font-weight: 500;
      line-height: 24px;
      letter-spacing: 0em;
      text-align: left;      
      color: #373753;
    }

    .chat-component-pesquisa{
      padding: 16px 18px 13px 18px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .chat-component-pesquisa form{
      display: flex;
      align-items: center;
    }

    .chat-component-pesquisa .btn-Pesquisa{
      background-color: transparent;
      border: none;
      margin-right: 16px;
    }

    .chat-component-pesquisa input{
      margin: 0;
      font-size: 16px;
      border: none;
      color: #373753;
    }

    .chat-component-pesquisa input:focus{
      outline: none;
    }

    .chat-component-pesquisa-icon{
      border: none;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #3057F2;
      border-radius: 10px;
      height: 32px;
      width: 32px;
      color: #FFFFFF;
    }

    .chat-component-pesquisa-icon:hover{
      background-color: #3057f2da;
      cursor: pointer;
    }

    .line-header{
      width: 100%;
      height: 1px;
      background-color: #E1E9F4;
    }

    .chat-component-areaContatos{
      border: solid 1px #D9DCE0;
      width:   330px;
      height:   100vh;
      overflow-y: scroll; 
      scrollbar-width: none;
      -ms-overflow-style: none; 
    }
    .chat-component-areaContatos::-webkit-scrollbar {
          display: none;
    }

    .area-contato{
      display: flex;
      justify-content: space-between;
      width: 100%;
    }

    .area-contato-left{
      display: flex;
      align-items: center;
      padding: 16px 8px;
    }
    .area-contato-left-texto{
      margin-left: 8px;
      text-align: left;
    }

    .area-contato-left-texto p{
      font-size: 16px;
      font-weight: 500;
      line-height: 24px;
      color: #1B1B2B;
    }

    .area-contato-left-texto span{
      font-size: 14px;
      font-weight: 400;
      line-height: 16px;
      letter-spacing: 0em;
      color: #373753;
    }
    .area-contato-right{
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: end;
      padding: 8px;
    }

    .area-contato-right p{
      font-size: 12px;
      font-weight: 400;
      line-height: 14px;
      letter-spacing: 0em;
      color: #373753;

    }

    .area-contato-right div{
      background-color: #3057F2;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 24px;
      width: 24px;
      border-radius: 50%;
      color: #FFFFFF;
      font-size: 12px;
      font-weight: 400;
      line-height: 16px;
      letter-spacing: 0em;
      text-align: center;
    }

    .lista-contatos{
      padding: 4px 8px;
      cursor: pointer;
    }

    .lista-contatos .ativo {
        background-color: #E1E9F4;
        border-radius: 10px;
        cursor: pointer;
    }
</style>