<template>
    <div class="chat" v-if="contatoAtual">
        <div class="chatHeader">
            <div class="chatHeader-itens-right">
                <img :src='contatoAtual.imgPerfil' width="40" height="40" alt=""> 
                <div class="chatHeader-texto">
                    <p class="nameContato">{{ contatoAtual.nome }}</p> 
                    <span class="agenteContato">Agente: Alanis Machado</span>
                </div>  
                </div>
            <div class="chatHeader-btns">
                <button class="btn-finalizar" @click="fecharChat">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="white" d="M10.5 15.25A.74.74 0 0 1 10 15l-3-3a.75.75 0 0 1 1-1l2.47 2.47L19 5a.75.75 0 0 1 1 1l-9 9a.74.74 0 0 1-.5.25"/><path fill="white" d="M12 21a9 9 0 0 1-7.87-4.66a8.67 8.67 0 0 1-1.07-3.41a9 9 0 0 1 4.6-8.81a8.67 8.67 0 0 1 3.41-1.07a8.86 8.86 0 0 1 3.55.34a.75.75 0 1 1-.43 1.43a7.62 7.62 0 0 0-3-.28a7.43 7.43 0 0 0-2.84.89a7.5 7.5 0 0 0-2.2 1.84a7.42 7.42 0 0 0-1.64 5.51a7.43 7.43 0 0 0 .89 2.84a7.5 7.5 0 0 0 1.84 2.2a7.42 7.42 0 0 0 5.51 1.64a7.43 7.43 0 0 0 2.84-.89a7.5 7.5 0 0 0 2.2-1.84a7.42 7.42 0 0 0 1.64-5.51a.75.75 0 1 1 1.57-.15a9 9 0 0 1-4.61 8.81A8.67 8.67 0 0 1 12.93 21z"/></svg>
                    Finalizar
                </button>
                <button class="btn-menu">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="#677c92" d="M7 12a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0m7 0a2 2 0 1 1-4 0a2 2 0 0 1 4 0"/></svg>
                </button>
            </div>
        </div>
       <div class="mensagens">
        <div class="infoChat">
            <p class="infoChatTexto">HOJE</p>
            <span class="infoChatTexto">Início do chamado pelo cliente. Protocolo: 1002356910  - 12:54 </span>
        </div>
            <div
            v-for="mensagem in mensagens[contatoAtual.id]"
            :key="mensagem.texto"
            :class="{ enviada: mensagem.de === 'Você', recebida: mensagem.de !== 'Você' }"
            >
                {{ mensagem.texto }} <span class="horaMns">{{ mensagem.horaMns }}</span>
            </div>
       </div>
       <InputComponent/>
    </div>
   </template>
   
<script>
import InputComponent from './inputComponent/inputComponent.vue';

   export default {
    props: ['contatoAtual', 'mensagens', 'novaMensagem', 'enviarMensagem'],
    components:{
    InputComponent
    },
    methods: {
        fecharChat() {
            this.$emit('fecharChat');
        }
    },
   };
</script>

<style scoped>
    .chat{
        display: flex;
        flex-direction: column;
        flex: 1;
        background-color: #E1E9F4;
        background-image: url('./../../../assets/Rectangle.png');
    }

    .chatHeader{
        height: 56px;
        width: 100%;
        background-color: #FFFFFF;
        padding: 5px 24px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        border-radius: 0px 0px 16px 0px;
    }
    .chatHeader-itens-right{
        display: flex;
        align-items: center;
    }

    .chatHeader-btns{
        display: flex;
        align-items: center;
    }

    .chatHeader-itens-right img{
        margin-right: 4px;
    }

    .chatHeader-texto .nameContato{
        font-size: 16px;
        font-weight: 500;
        line-height: 24px;
        letter-spacing: 0em;
        text-align: left;
        color: #1B1B2B;
    }

    .chatHeader-texto .agenteContato{
        font-size: 12px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: left;
        color: #677C92;
    }

    .btn-finalizar{
        display: flex;
        gap: 7px;
        align-items: center;
        font-size: 14px;
        font-weight: 500;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: left;
        background-color: #3057F2;
        color: #FFFFFF;
        border: none;
        border-radius: 10px;
        padding: 7px 13px;
    }

    .btn-finalizar:hover{
        background-color: #3057f2da;
        cursor: pointer;
    }

    .btn-menu{
        display: flex;
        justify-content: center;
        align-items: center;
        border: none;
        width: 32px;
        height: 32px;
        border-radius: 8px;
        background-color: #E1E9F4;
        margin-left: 16px;
        cursor: pointer;
    }

    .btn-menu:hover{
        background-color: #e1e9f48c;
    }

    .mensagens {
        display: flex;
        flex-direction: column;
        width: 100%;
        overflow-y: auto;
        padding: 21px 24px;
        height: 100%;
    }

    .infoChat{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 12px;
        margin-bottom: 28px;
    }

    .infoChat .infoChatTexto{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 28px;
        padding: 12px;
        border-radius: 10px;
        background-color: #FFFFFF;
        font-size: 12px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: center;

    }

    .mensagens .recebida {
        display: flex;
        align-items: center;
        font-size: 15px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        color: #1B1B2B;
        height: 28px;
        padding: 12px;
        border-radius: 8px 8px 8px 0px;
        background-color: #FFFFFF;
        width: fit-content;
    }

    .horaMns{
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        font-size: 10px;
        font-weight: 500;
        line-height: 17px;
        letter-spacing: 0em;
        color: #1B1B2B;
        padding: 0 6px;
    }

</style>