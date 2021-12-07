<template>
  <Header />
  <ul v-show="show" class="list-group" style="margin-left: 5px">
    <li :key="task" v-for="task in tasks" class="list-group-item" :class="task.priority" style="width: 500px">
      {{ task.name }}
    </li>
  </ul><br>

  <button v-if="!show" @click="changeShow" class="btn btn-secondary" style="margin-left: 5px">Show tasks</button>
  <button v-else @click="changeShow" class="btn btn-secondary" style="margin-left: 5px">Hide Tasks</button><br><br>

  <label for="task" style="margin-left: 5px">New task: </label>
  <input type="text" id="newTask" name="task" v-model="newTask" style="margin-left: 10px;"/><br><br>

  <div v-show="invalidNewTask" class="alert alert-warning" role="alert" style="width: 500px">Please enter a non empty value!</div>
  <button @click="addNewTask()" class="btn btn-success" style="margin-left: 5px">Add Task</button>

  

  
</template>


<script>

import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
  },
  data() {
    return {
      tasks: [
                {name: "Learn React", priority: "Low"},
                {name: "Learn Vue", priority: "Medium"},
                {name: "Become a Web-Programmer", priority: "High"},
                ],
            show: true,
            newTask: "",
            invalidNewTask: false,
    } 
  },
  methods: {
        changeShow(){
            this.show = !this.show;
        },
        addNewTask(){
            if(this.newTask === ""){
                this.invalidNewTask = true;
                return;
            }
            newTask = {name: this.newTask, priority: "Medium"}
            this.tasks.push(newTask);
            this.newTask = "";
            this.invalidNewTask = false;
         },
    },
    computed: {
    }
}
</script>


<style>
.High {
    background-color: lightcoral;
}

.Medium {
    background-color: lightsalmon;
}

.Low {
    background-color: bisque;
}
</style>
