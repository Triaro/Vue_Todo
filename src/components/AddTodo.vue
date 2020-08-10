<template >
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title"
             placeholder="AddTodo...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>


<script >
//import uuid1 from 'uuid';
//import Vue from "vue";
//import uuid from "vue-uuid";
//Vue.use(uuid);
//const { v4: uuidv4 } = require('uuid');

export default{
   name: "AddTodo",
   data(){
       return{
           title: ''
       }
   },
   methods: {
       addTodo(e){
           e.preventDefault();
           const newTodo = {
              // id: uuidv4(),
               title: this.title,
               completed: false
           }
           //Send up to parent
           this.$emit('add-todo', newTodo);
            this.title='';
       }
   }
}
</script>

<style scoped>
 form{
     display: flex;
 }

 input[type="text"]{
     flex: 10;
     padding: 5px;
 }

 input[type="submit"]
{  flex: 2;
}
</style>
