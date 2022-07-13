<template>
  <div id="app">
    <div v-show="!logins.email">
      Log In<br>
      <form style="padding:16px;" @submit.prevent="login">
        Email<br>
        <input type="email" id="email" v-model="email"><br>
        Password<br>
        <input type="password" id="pass" v-model="pass"><br>
        <button type="submit">LOG IN</button>
      </form>
    </div>
    <div v-show="logins.email"> 
      <div style="width:98vw; height:200px; background-color:red; display:flex; justify-content: space-between; align-items: center;">
        <span>{{logins.email.substring(10,0) }}</span>
        <button v-on:click="logout()">LOG OUT</button>
      </div>
     Selamat ...<br><br>
     {{ logins.email }} <br><br>
     Jam ... <br><br>
     {{ get }}
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      email: "",
      pass: "",
      logins: {
        email: "",
        pass: ""
      }
    }
  },
  methods:{
    login(){
      if(this.email.length > 10 && this.email.length > 15) {
        if(this.email == "aaaaaaaaaa@gmail.com" && this.pass == "Bebenia@123"){
          this.logins.email = this.email;
          this.logins.pass = this.pass;
          alert("yeaaaa boii")
        } else {
          alert("username password salah")
        }
      } else {
        alert("wrong format")
      }
    },
    logout() {
      this.logins.email = "";
      this.logins.pass = "";
      alert("byeee boii")
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
