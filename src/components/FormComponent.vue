<template>
  <MessageComponent :msg="msg" v-show="msg"/>
  <ErrorComponent :error="error" v-show="error"/>
  <div class="contact">
    <form class="contact_form" @submit="contactSubmit">
      <div class="input_container">
        <label for="nome">Nome Completo:</label>
        <input type="text" name="nome" id="nome" v-model="nomeData" placeholder="Digite seu nome">
      </div>
      <div class="input_container">
        <label for="nome">Email:</label>
        <input type="email" name="nome" id="nome" v-model="emailData" placeholder="Digite seu email">
      </div>
      <div class="input_container">
        <label for="nome">Tefelone:</label>
        <input type="tel" name="nome" id="nome" v-model="numPhoneData" placeholder="Digite seu número">
      </div>

      <div>
        <input type="submit" value="Enviar!" class="submit_btn">
      </div>
    </form>
  </div>
</template>

<script>
import MessageComponent from '../components/MessageComponent.vue'
import ErrorComponent from '../components/ErrorComponent.vue'

export default {
  components:{
    MessageComponent,
    ErrorComponent

  },
  data(){
    return{
      nomeData: '',
      emailData: '',
      numPhoneData: '',
      msg: '',
      error:''
    }
  },methods:{
    contactSubmit(e){
      e.preventDefault();

      if (this.nomeData == "") {
        this.error = `Erro no campo de Nome!`
      }else if(this.emailData == "") {
        this.error = `Erro no campo de Email!`
      }else if (this.numPhoneData == "") {
        this.error = `Erro no campo de Telefone!`
      }else{
        this.error = '';
        this.msg = `${this.nomeData} foi cadastrado, entraremos em contato em breve!`;

        this.nomeData = '',
        this.emailData = '',
        this.numPhoneData = ''
      }
      setTimeout(() => this.msg = "", 5000); 
      setTimeout(() => this.error = "", 3000);

    }
  }
}
</script>

<style scoped>
.contact{
  min-height:calc(100vh - 140px);
  background-color: #ddd;
  display:flex;
  align-items: center;
  justify-content: center;
}

.contact_form{
  display:flex;
  flex-direction: column;
  gap:30px;
  padding:50px 10px;
  background-color: #eee;
}

.input_container *{
  width:100%;
}

.input_container input{
  padding: 4px 12px;
}

.submit_btn{
  padding: 8px 16px;
  background-color: #1034c2;
  border:none;
  color:white;
}
</style>