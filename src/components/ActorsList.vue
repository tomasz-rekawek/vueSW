<template>
  <div class="hello">
      <li v-for="(item) in items" :key="item.name">
        {{item.name}}
      </li>
  </div>
</template>

<script>
import axios from 'axios';


export default {
  name: 'ActorsList',
  props: {
    msg: String
  },
  data: () => {
      return { items: [
        {name: 'waiting'},
        {name: 'for'},
        {name: 'answer'}
      ]
    }
  },
  created () {
    axios.get('https://swapi.co/api/people/?page=1')
      .then( res => {
        console.log(res);
        return res.data;
        })
      .then( res => res.results)
      .catch( error => {
        console.log(error)
      })
      .then( res => {
        console.log(res);
        this.items = res;
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
