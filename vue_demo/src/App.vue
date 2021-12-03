<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div class="row">
    <div class="col-6">
      <buttonVue @inputData="add" @editdata="edit"></buttonVue>
    </div>
   <div class="col-6">
      <tableVue v-bind:todos="todos"  @deletedata="deleteVue" ></tableVue>
    </div>
    </div>
    

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import buttonVue from './components/button.vue'
import tableVue from './components/table.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld
    buttonVue,
    tableVue
  },
  data(){
    return{
      todos: [
        {
          name: 'Huyen',
          age: '18',
          active: true
        },
        {
          name: 'Hue',
          age: '28',
   active: false
        },
        {
          name: 'Huy',
          age: '30',
            active: true
        }
      ]
    }
   

  },
  methods:{
    add(name,age){
      this.todos.push({name:name,age:age})
    },
    edit(index,name,age){
      this.todos.splice(index,1 , {name:name, age:age})
    },
    deleteVue(index){
      this.todos.splice(index,1)
    }
  },
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
