<template>
 <div class="chat-component">
    <ContactsList
      :contatos="contatos"
      :selecionarContato="selecionarContato"
      :contatoAtual="contatoAtual"
    />
    <ChatArea
      :contatoAtual="contatoAtual"
      :mensagens="mensagens"
      v-model:novaMensagem="novaMensagem"
      :enviarMensagem="enviarMensagem"
      @fecharChat="contatoAtual = null"
    />
 </div>
</template>
  
<script>

  import ContactsList from './ContactsList/ContactsList.vue';
  import ChatArea from './ChatArea/ChatArea.vue';


  export default {
    components: {
    ContactsList,
    ChatArea,
    },
    data() {
        return {
            contatos: [
                { id: 1, nome: 'Abner José Campos', imgPerfil: require('@/assets/Avatares/Avatar.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Então, vou pagar dia 6 as du...', mnsNLidas: 0 },
                { id: 2, nome: 'Elaine Da Silva', imgPerfil: require('@/assets/Avatares/Avatar-1.png'), dataUltimaConversa: '13/04', textoUltimaConversa: 'Foi você que me ligou?', mnsNLidas: 16 },
                { id: 3, nome: 'Camila Aparecida', imgPerfil: require('@/assets/Avatares/Avatar-2.png'), dataUltimaConversa: '13/04', textoUltimaConversa: 'Você: ahh entendi!', mnsNLidas: 16 },
                { id: 4, nome: 'Jose Batista Souza', imgPerfil: require('@/assets/Avatares/Avatar-3.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Arquivo', mnsNLidas: 0 },
                { id: 5, nome: 'Léia De Souza Bueno', imgPerfil: require('@/assets/Avatares/Avatar-4.png'), dataUltimaConversa: '13/04', textoUltimaConversa: 'Meu pagamento caiu ai?', mnsNLidas: 16 },
                { id: 6, nome: 'Júlio Santos', imgPerfil: require('@/assets/Avatares/Avatar-5.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Foto', mnsNLidas: 0 },
                { id: 7, nome: 'Julio Cesar Lopes', imgPerfil: require('@/assets/Avatares/Avatar-6.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Meu pagamento caiu ai?', mnsNLidas: 0 },
                { id: 8, nome: 'Carlos Tozeli', imgPerfil: require('@/assets/Avatares/Avatar-7.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Meu pagamento caiu ai?', mnsNLidas: 0 },
                { id: 9, nome: 'Grasielle Castro', imgPerfil: require('@/assets/Avatares/Avatar-8.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Posso mandar áudio?', mnsNLidas: 0 },
                { id: 10, nome: 'Ítala Farias', imgPerfil: require('@/assets/Avatares/Avatar-9.png'), dataUltimaConversa: '09:13', textoUltimaConversa: 'Vídeo', mnsNLidas: 0 },
            ],
            mensagens: {
                1: [
                    { de: 'Abner José Campos', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
                2: [
                    { de: 'Elaine Da Silva', texto: 'Como você está?', horaMns: '11:29' },
                ],
                3: [
                    { de: 'Camila Aparecida', texto: 'Como você está?', horaMns: '11:29' },
                ],
                4: [
                    { de: 'Jose Batista Souza', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
                5: [
                    { de: 'Léia De Souza Bueno', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
                6: [
                    { de: 'Júlio Santos', texto: 'Como você está?', horaMns: '11:29' },
                ],
                7: [
                    { de: 'Julio Cesar Lopes', texto: 'Como você está?', horaMns: '11:29' },
                ],
                8: [
                    { de: 'Carlos Tozeli', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
                9: [
                    { de: 'Grasielle Castro', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
                10: [
                    { de: 'Ítala Farias', texto: 'Quero pagar minha fatura mas não consigo', horaMns: '11:29' },
                ],
            },
            contatoAtual: null,
            novaMensagem: '',
        };
    },
    methods: {
        selecionarContato(id) {
            this.contatoAtual = this.contatos.find(contato => contato.id === id);
        },
        // enviarMensagem(texto) {
        //     if (!this.contatoAtual)
        //     return;
        //     this.mensagens[this.contatoAtual.id].push({ de: 'Você', texto });
        //     this.novaMensagem = '';
        // }
    }
};
</script>
  
<style scoped>
    .chat-component{
        display: flex;
        margin: 0%;
        width: 100%;
    }

</style>