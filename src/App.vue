<template>
 <div>
   <h1>Movie</h1>
    <div class="input">
      <input type="search" v-model="search">
      <button @click="getposts">search</button>
    </div>

    <div class="result">
      <ul>
        <li v-for="post in post" :key="post">{{ post }}</li>
      </ul>
    
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      post: [],
      search:''
    }
  },
  methods: {
    getposts(){
      fetch(`http://www.omdbapi.com/?i=tt3896198&apikey=96b56e3b`)
      .then(Response => Response.json())
      .then(data => this.post = data)
    }
  }
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
  margin-top: 60px;
}

.result{
  background-color: rgb(87, 149, 190);
}
</style>
