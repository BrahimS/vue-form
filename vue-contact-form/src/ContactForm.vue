<template>
  <form>
    <div 
      class="form-group"
      :class=" {'invalid-field' : !isValidEmail }"
    >
      <label for="sender-email">Email</label>
      <input 
        type="email" 
        class="form-control"
        id="sender-email"
        v-model="email"
      >
    </div>
    <div class="form-group"
      :class="{'invalid-field' : !message }"
    >
      <label for="sender-email">Message</label>
      <textarea 
          name="sender-message" 
          type="text" 
          class="form-control"
          id="sender-message"
          cols="30" 
          rows="10"
          v-model="message"
        >
      </textarea>
    </div>
    <div class="form-group">
        <button class="btn btn-primary"
        :disabled="!isValidEmail || !message"
          @click.prevent="submitForm"
        >
      Send Message
      </button>
    </div>
  </form>
</template>
<script>
export default {
  data() {
    return {
      email: '',
      message: ''  
    };
  },
  computed: {
    isValidEmail() {
      let re= /^\w+@[a-zA-Z_]+?\.[a-zA-Z]{2,3}$/;
        return re.test(this.email);
      }
  },
 methods: {
   submitForm() {
    alert( `Thanks, your message is ${this.message}. I will replay to this ${this.email} soon`)
   }
 }
}
</script>
<style scoped>
.invalid-field .form-control{
  border-color: #dc3545;
  border-width: 2px;
  }
  .invalid-field label{
    color: #dc3545;
    font-weight: bold;
  }
</style>