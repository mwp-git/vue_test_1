
<template>
  <div>
    <h1>Submit data to API</h1>

    <input placeholder="Username" v-model="user.username"><br><br>
    <input placeholder="Password" v-model="user.password"><br><br>
    <button v-on:click="login" >Post</button>

  </div>

</template>

<script>

import axios from 'axios'

export default{
  name:"PostComponent",
  data(){
    return{
      user:{
        username:null,
        password:null
      }
    }
  },

  methods:{
    async login(e){
      const res = await axios.post('https://backend.mama.sh/api/login', this.user);
      const tkn = await res.json();
      }
    }
}
</script>
