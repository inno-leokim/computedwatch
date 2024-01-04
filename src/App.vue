<template>
  <div id="app">
    <div>
      <h4>computed</h4>
      {{ message }}
      <h4>Reverse Message</h4>
      {{ reverseMessage }}
    </div>
    <div>
      <h4>Watch</h4>
      <input v-model="firstname" />
      <input v-model="lastname" />
      <br>
      <p>full name</p>
      <span>{{ fullname }}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data(){
      return {
        message: 'Hello Vue!!',
        firstname: '',
        lastname: '',
        fullname: ''
      }
    },
    computed: {
      reverseMessage() {
        return this.message.split("").reverse().join("")
      }
    },
    watch: { // watch에서 함수이름은 감시할 state값과 이름을 동일하게 설정한다.
      firstname(val){
        this.fullname = `${val} ${this.lastname}`
      },
      lastname(val){
        this.fullname = `${this.firstname} ${val}`
      }
    }    
  }
</script>

<style>
</style>
