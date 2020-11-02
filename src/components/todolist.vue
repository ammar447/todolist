<template>
  <div id="todo" class="cont">
         <h1> Add your daily tasks </h1>
    <div class="todolist"  >
       
    <form action="">
      <input type="text" placeholder="add your tasks" v-model="texttask" />
      <button  class="butt"  @click.prevent="addtask" :disabled="!texttask" >add</button>
      <button class="butt" @click.prevent="deleteall"  v-if="tasks.length > 1" >delete all</button>
    </form>
    <div>
      <div v-for="(task, index) in tasks" :key="index">
          <div style="margin-top: 50px;" > 
                <div   class="text"
                @click="task.done= !task.done"
               :style="{ 'text-decoration': task.done ? 'line-through' : '' }"  >
                  
                {{task.words}}
                </div>
                 <button class="butt fl" @click="deletetask(index)" >delete</button> 
          </div>
      </div>
      
    </div>
    </div>  
  </div>
</template>

<script>
 
 
export default {
      data: function () {
            return {
                  tasks: [],
                  texttask: "",
            }
        },
     methods: {
    addtask: function() {
     this.tasks.push({words: this.texttask, done: false});
     this.texttask="";
    },
    deletetask : function (index) {
        this.tasks.splice(index,1)
    },
    deleteall : function () {
        this.tasks = [];
    },
   
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Lato:ital@1&display=swap');
 
.cont {
       background-color: #85c1e9;
    text-align: center;
    padding-top: 155px;
    margin-top: -3px;
    height: auto;
    padding-bottom: 175px;
 font-family: 'Lato', sans-serif;
}
.cont .todolist {
   background-color: #FFF;
    margin: 0 auto; 
    padding: 75px;
    border-radius: 5%;
    height: auto;
    width: 30%;
     
}
.cont .todolist input {
     padding: 10px;
     margin-bottom: 25px;
}
.cont .todolist .text {
      background-color: #0b4d5c;
      color: #FFF;
    display: initial;
    padding: 15px;
    margin-left: -167px;
}
.cont .todolist .butt {
    background: none;
    font-size: 15px;
    margin-left: 20px;
    padding: 10px;
    font-weight: bold;
    color: #0b4d5c;
    border: 1px solid #0b4d5c;
    cursor: pointer;
    border-radius: 15%;

}
.cont .todolist .fl {
  float: right;
}
  
</style>