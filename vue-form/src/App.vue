<template>
  <div>
    <form action="" v-on:submit.prevent="submitForm">
      <div>
        <label for="username">id: </label>
        <input id="usernaem" type="text" v-model="username">
      </div>
      <div>
        <label for="password">password: </label>
        <input type="password" name="" id="password" v-model="password">
      </div>
      <button type="submit">login</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data: function(){
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    submitForm: function(){
      //event.preventDefault();
      console.log(this.username);
      var url ='https://jsonplaceholder.typicode.com/users'
      var data = {
        username: this.username,
        password: this.password,
      }
      axios.post(url, data)
        .then(function(response){
          console.log(response);
        })
        .catch(function(error){
          console.log(error);
        })
    }
  }
}
</script>

<style>

</style>