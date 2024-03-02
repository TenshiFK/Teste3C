<template>
    <div class="Responder">
        <div class=" ResponderHeader">
            <p>Responder ao Cliente</p>
            <div class="ResponderIcons">
                <button @click="toggleModal"><svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="#677c92" d="M19 5v9h-5v5H5V5zm0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h10l6-6V5c0-1.1-.9-2-2-2m-7 11H7v-2h5zm5-4H7V8h10z"/></svg></button>
                <button><svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><g fill="none" stroke="#677c92" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><path d="M22 11v1a10 10 0 1 1-9-10"/><path d="M8 14s1.5 2 4 2s4-2 4-2M9 9h.01M15 9h.01M16 5h6m-3-3v6"/></g></svg></button>
                <button><svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="#677c92" d="M8.94 20.74a5.85 5.85 0 0 1-4-1.56a5.23 5.23 0 0 1 0-7.68l7.56-7.14a4.22 4.22 0 0 1 5.69 0A4.1 4.1 0 0 1 19.5 7.3a3.46 3.46 0 0 1-1.1 2.55L10.83 17a2.47 2.47 0 0 1-3.36 0a2.23 2.23 0 0 1 0-3.28l7-6.59a.75.75 0 0 1 1.06 0a.75.75 0 0 1 0 1.06l-7 6.59a.73.73 0 0 0 0 1.1a1 1 0 0 0 1.3 0l7.57-7.13A2 2 0 0 0 18 7.3a2.57 2.57 0 0 0-.84-1.84a2.67 2.67 0 0 0-3.63 0L6 12.59a3.73 3.73 0 0 0 0 5.5a4.4 4.4 0 0 0 6 0L19.49 11a.74.74 0 0 1 1.06 0a.75.75 0 0 1 0 1.06L13 19.18a5.84 5.84 0 0 1-4.06 1.56"/></svg></button>
            </div>
        </div>
        <div class="ResponderFooter">
            <textarea placeholder="A 3C Plus é uma empresa de tecnologia que se especializa em fornecer soluções para ajudar outras empresas a aprimorar suas operações de atendimento ao cliente. Suas ofertas podem incluir uma variedade de serviços e produtos projetados para otimizar as interações entre as empresas e seus clientes, independentemente do canal de comunicação utilizado."/>
            <button class="btn-send">
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 16 16"><path fill="#677c92" d="m1 1.91l.78-.41L15 7.449v.95L1.78 14.33L1 13.91L2.583 8zM3.612 8.5L2.33 13.13L13.5 7.9L2.33 2.839l1.282 4.6L9 7.5v1z"/></svg>
            </button>
        </div>
    <ModalComponent v-show="isModalVisible">
        <div class="ResponderModal">
            <div class=" ResponderModalHeader">
                <p>Nota interna</p>
                <div class="ResponderModalIcons">
                    <button @click="toggleModal" class="fecharModal"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="#bf810a" d="M6.4 19L5 17.6l5.6-5.6L5 6.4L6.4 5l5.6 5.6L17.6 5L19 6.4L13.4 12l5.6 5.6l-1.4 1.4l-5.6-5.6z"/></svg></button>
                    <button><svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><g fill="none" stroke="#677c92" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><path d="M22 11v1a10 10 0 1 1-9-10"/><path d="M8 14s1.5 2 4 2s4-2 4-2M9 9h.01M15 9h.01M16 5h6m-3-3v6"/></g></svg></button>
                    <button><svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path fill="#677c92" d="M8.94 20.74a5.85 5.85 0 0 1-4-1.56a5.23 5.23 0 0 1 0-7.68l7.56-7.14a4.22 4.22 0 0 1 5.69 0A4.1 4.1 0 0 1 19.5 7.3a3.46 3.46 0 0 1-1.1 2.55L10.83 17a2.47 2.47 0 0 1-3.36 0a2.23 2.23 0 0 1 0-3.28l7-6.59a.75.75 0 0 1 1.06 0a.75.75 0 0 1 0 1.06l-7 6.59a.73.73 0 0 0 0 1.1a1 1 0 0 0 1.3 0l7.57-7.13A2 2 0 0 0 18 7.3a2.57 2.57 0 0 0-.84-1.84a2.67 2.67 0 0 0-3.63 0L6 12.59a3.73 3.73 0 0 0 0 5.5a4.4 4.4 0 0 0 6 0L19.49 11a.74.74 0 0 1 1.06 0a.75.75 0 0 1 0 1.06L13 19.18a5.84 5.84 0 0 1-4.06 1.56"/></svg></button>
                </div>
            </div>
            <div class="ResponderModalFooter">
                <textarea>Mensagem</textarea>
                <button class="btn-sendModal">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 16 16"><path fill="#BF810A" d="m1 1.91l.78-.41L15 7.449v.95L1.78 14.33L1 13.91L2.583 8zM3.612 8.5L2.33 13.13L13.5 7.9L2.33 2.839l1.282 4.6L9 7.5v1z"/></svg>
                </button>
            </div>
        </div>
    </ModalComponent>
</div>
</template>

<script>
import ModalComponent from '../../../ModalComponent/ModalComponent.vue';
export default {
    component:{
        ModalComponent
    },
    data() {
        return {
            isModalVisible: false,
        };
    },
    methods: {
        toggleModal() {
            this.isModalVisible = !this.isModalVisible;
        },
    },
}
</script>

<style scoped>
    .Responder{
        width: 100%;
        height: 190px;
        background-color: #FFFFFF;
        border-top: solid #DFDFDF 1px;
        padding: 12px 32px 32px 32px;
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
        color: #1B1B2B;
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
        cursor: pointer;
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

    .ResponderModal{
        width: 865px;
        height: 135px;
        background-color: #FFFFFF;
        border-top: solid #DFDFDF 1px;
        padding: 12px 32px 32px 32px;
        position: fixed;
        z-index: 1000;
        bottom: 80px;
        overflow: auto;
        box-shadow: 0px 3px 8px 0px #0000003D;
    }

    .ResponderModal textarea{
        resize: none;
        width: 100%;
        height: 40px;
        text-align: justify;
        padding: 12px 24px;
        background-color: #FFE9A9;
        border-radius: 8px;
        border: none;
        font-size: 14px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: left;
        scrollbar-width: none;
        -ms-overflow-style: none; 
        color: #754000;
    }
    .ResponderModal textarea::-webkit-scrollbar {
            display: none;
    }

    .fecharModal{
        background-color: #FFBB3A !important;
        height: 32px;
        width: 32px;
        border-radius: 8px;
    }

    .fecharModal:hover{
        background-color: #ffba3a8e !important;
    }

    .btn-sendModal{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: none;
        background-color: #FFE9A9;
        height: 40px;
        width: 40px;
        border-radius: 8px;
        margin-left: 8px;
    }

    .btn-sendModal:hover{
        background-color: #e6d298;
        cursor: pointer;
    }

    .ResponderModalHeader, .ResponderModalFooter{
        display: flex;
        align-items: center;
    }

    .ResponderModalHeader{
        justify-content: space-between;
        margin-bottom: 16px;
    }

    .ResponderModalHeader p{
        width: 100%;
        font-size: 16px;
        font-weight: 500;
        line-height: 24px;
        letter-spacing: 0em;
        text-align: left;
        color: #373753;        
        border-bottom: solid 1.3px #E1E9F4;
    }

    .ResponderModalIcons{
        display: flex;
        gap: 14px;
        margin-left: 14px;
    }

    .ResponderModalIcons button{
        border: none;
        background-color: transparent;
        cursor: pointer;
    }

    .ResponderModalFooter{
        align-items: end;
    }
</style>
