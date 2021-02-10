<template>
  <div class="container">


  </div>

</template>



<script>
import axios from "axios";
export default {
  name: 'API',
  props: {
    msg: String
  },
data (){
  return{
    users : null
  }
},
 created: function(){
   axios.get('https://jsonplaceholder.typicode.com/users')
   .then(res => {
     this.users = res.data;
   })
 },
 }
</script>




<style scoped>
h3 {
  margin: 4px 0 0;
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
