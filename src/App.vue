
<template>
  <div class="container">
    <h1>App Users List</h1>
    
    <table class="table">
  <thead>
    <tr>
      <th scope="col">#ID</th>
      <th scope="col">Name</th>
      <th scope="col">Email</th>
      <th scope="col">Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr v-bind:key="user.id" v-for="user in users">
      <th scope="row">{{user.id}}</th>
      <td>{{user.name}}</td>
      <td>{{user.email}}</td>
      <td>{{user.phone}}</td>
    </tr>
    
  </tbody>
</table>


  </div>

    <!-- <font-awesome-icon icon="user-secret" /> -->
    <!-- <h1>Todos</h1>
    <input type="text" v-model="todoName" @keyup.enter="addTodo">
    <button @click="addTodo">Add</button>
    <ul>
      <li v-for="todo of todos" :key="todo.id">{{todo.name}}
        </li>
        <button v-for="todo of todos" :key="todo.id" @click="removeTodo">X
        </button>
         
    </ul>
    
  </div>

  <API msg="Welcome to Your Vue.js App" /> -->
</template>

<script>
import axios from "axios";

export default {
  name: 'API',
  // props: {
  //   msg: String
  // },
//   data(){
//     return{
//       users : null,
//     }
//   },
//   created: function(){
//     axios.get('https://jsonplaceholder.typicode.com/users')
//     .then(Response =>{
//       this.users = Response.data;
//     })
//   }
// }

data (){
  return{
    users : []
  }
},
 created: function(){
   axios.get('https://jsonplaceholder.typicode.com/users')
   .then(res => {
     this.users = res.data;
   })
 }
}
// import API from './components/API'
 
// const mainURL = 'http://localhost:3000/todos';
// export default {
//   name: "App",
//   data(){
//     return{
//       todos : [],
//       todoName : ''
//     };
//   },
//   async created(){
//     try{
//       const res = await axios.get(mainURL);
//       this.todos = res.data;  
//     } catch(e){
//       console.log(e)
//     }
//   },
//   methods:{
//     async addTodo(){
//       const res = await axios.post(mainURL, {name: this.todoName})
//       this.todos = [...this.todos, res.data]
//       this.todoName =  ""
//     },
//     async removeTodo(){
//       const deletItem = await axios.delete(mainURL, {name: this.todoName})
//       this.todos = [...this.todos, deletItem.data]
//       }
//   }
// }
</script>

<style>
.container{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} 

.list-group{
  margin: 10em auto;
}
</style>
