<template>
    <div>
       <div class="item">
            <label for="">Nhap Ten :</label>
             <input type="text" v-model="name">
       </div>
       <div class="item">
            <label for="">Nhap Tuoi:</label>
             <input type="text" v-model="age">
       </div>
       <div class="item">
            <button class="btn-warning" v-on:click="addsend">ADD</button>
            <button class="btn-warning" v-on:click="editsend">EDIT</button>
            <button class="btn-warning">DELETE</button>
       </div>
    </div>
</template>
<script>

import EventBus from '../eventBus.js'
export default {
 data(){
    return{
        index:'',
      name:'',
      age:'',
     
    }
  },
    mounted() {
    EventBus.$on("editData", (item,index) => {
        // console.log(index)
        this.index=index;
    this.name=item.name;
    this.age=item.age;
    });
  },
   methods:{
    addsend(){
       this.$emit('inputData',this.name, this.age )
       this.name ="";
       this.age=""
    },
    editsend(){
        this.$emit('editdata', this.index,this.name, this.age)
    }
   }
}
</script>
