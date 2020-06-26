<template>
  <div class="contain pt-5">
    <h2 class="text-center font-weight-bold"> Random Pickup Lines 😉</h2>
    <div class="container d-flex flex-column">
      <div class="container h-100 pt-5 d-flex flex-column justify-content-center align-items-center">
        <h2 class="bold text-center">{{joke}}</h2>
        <h6 class="bold">By: {{user}}</h6>
      </div>
      <b-button class="mx-auto mt-5" variant="success" v-on:click="postJoke">another one</b-button>
    </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'jokes',
  data() {
    return {
      joke: '',
      user: ''
    }
  },
  methods: {
    postJoke(){
      axios.get('http://pebble-pickup.herokuapp.com/tweets/random').then((res)=> {
        const presentJoke = res.data.tweet;
        const user = res.data.username;
        this.joke = presentJoke;
        this.user = user;
      })
      .catch((res)=> {
        if(res instanceof Error){
          console.log(res.message);
        }
      })
    }
  },
  created(){
    this.postJoke();
  }
  
}
</script>

<style scoped>
  .contain{
    background-color: darkslategrey;
    color: #fff;
    height: 100vh;
    width: 100%;
  }
  .container > h2 {
    max-width: 500px;
  }
</style>
