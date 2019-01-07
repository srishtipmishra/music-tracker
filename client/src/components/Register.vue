<template>
  <div>
    <div class="formStyle" >
      <p>Registration</p>
      <div>
        <div class="form-input">
          <label class="title" for="username">Username:</label>
          <input type="text" id="username" placeholder="username" v-model="username"/>
        </div>
        <div class="form-input">
          <label class="title" for="password">Password:</label>
          <input type="password" id="password"  placeholder="password" v-model="password"/>
        </div>
        <button @click="register">Register</button>
      </div>
    </div>
  </div>
</template>

<script>
// import axios from 'axios'
import AuthenticationService from '../services/AuthenticationService.js'

export default {
  name: 'Register',
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    register () {
      console.log('in register')
      AuthenticationService.register({
        username: this.username,
        password: this.password
      })
        .then(response => {
          console.log(response.data)
        })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title {
  float: left;
  width: 100px;
  text-align: right;
  padding-right: 10px;
}
.radio-buttons label {
  float: none;}
.submit {
  text-align: right;}
.formStyle{
  border-bottom: 1px solid #efefef;
  margin: auto;
  padding-bottom: 10px;
  width: 260px;
}
.form-input{
  margin-bottom: 5px;
}
</style>
