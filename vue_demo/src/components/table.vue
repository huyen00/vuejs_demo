<template>
    <div>
        <table class="table">
            <tr>
                <th>STT</th>       
                <th>Ten</th>    
                <th>Tuoi</th>  
                <th>action</th>      
            </tr>
             <tr v-for="(item,index) in todos" :key="index" v>
                  <td>{{index}}</td>
                  <td>{{item.name}}</td>
                  <td>{{item.age}}</td>
                  <td><button v-on:click="clickTable(item,index)">Edit</button>
                 <button v-on:click="deleteVue(index)">Delete</button>
                  </td>
            </tr>
        </table>
    </div>
</template>
<script>

import EventBus from '../eventBus.js'
export default ({
  props:['todos'],
  methods:{
       clickTable(item,index){
        EventBus.$emit('editData', item,index);

    },
    deleteVue(index){
        this.$emit('deletedata',index)
    }
  }
  
})
</script>
