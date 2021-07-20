<template>
  <div id="app">
    <div class="home">
      <input type="text" v-model="postcode" maxlength="7">
      <button @click="search()">住所自動入力</button>
      <p>Address:</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default{
  data() {
    return {
      postcode:""
    };
  },
    methods: {
      async search(){
        await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/1000001?apikey=scXXQD1i29VdtnFS1QOuruB2oG6GIyNseCmaqEW`);
        .then(response =>{
          console.log(response);
        });
      }
    }
  };
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
