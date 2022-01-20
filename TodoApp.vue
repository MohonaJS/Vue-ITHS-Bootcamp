<template>
  <div class="container">
     <h2 class="text-center mt-5">My vue ToDo App </h2>

     <!-- input -->
     <div class="d-flex">
         <input @keypress.enter="submitTask"  v-model="task" type="text" placeholder="Enter task" class="form-control">
         <button 
          @click="submitTask" class="btn btn-warning rounded-0" > Submit </button>
     </div>
         <!-- Tast table -->
        <table class="table table-bordered mt-5">
  <thead>
    <tr>
      <th scope="col">Task</th>
      <th scope="col">Satus</th>
      <th scope="col" class="text-center">#</th>
      <th scope="col" class="text-center">#</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(task, index) in tasks" :key="index">
      <td>{{task.name}}</td>

      <td> <span @click="changeStatus(index)" class="pointer">{{task.status}}</span> </td>

      <td> 
          <div class="text-center" @click="editTask(index)">
              <span class="fa fa-pen"></span>
          </div>
      </td>
      <td>
          <div class="text-center"  @click="deleteTask(index)">
              <span class="fa fa-trash"></span>
          </div>
      </td>
    </tr>
  </tbody>
</table>
  </div>
</template>

<script>
export default {
    name:'Helllowords',
    props: {msg: String},
    data(){
        return{  
            task: '',
            editedTast: null,
            availableStatus: ['to-do', 'in-progress', 'finished'],
            tasks: [
                {  
                    name: 'Buy fruit', status:'to-do', 
                },
                {  
                    name: 'Buy Vegitables', status:'in progress', 
                }
            ]

        }},
    methods: {
            submitTask(){  
                if(this.task.length ===0) return;

                if(this.editedTast === null){ 
                    this.tasks.push({
                    name: this.task,
                    status: 'to-do'
                }) }
                else {  
                    this.tasks[this.editedTast].name = this.task;
                    this.editedTast = null;
                }
                
                this.task = '';
            },
            deleteTask(index){  
                this.tasks.splice(index,1)
            },
            editTask(index){  
                this.task = this.tasks[index].name;
                this.editedTast = index;
            },
            changeStatus(index){
               let newIndex =  this.availableStatus.indexOf(this.tasks[index].status)
               if(++newIndex > 2) newIndex = 0;
               this.tasks[index].status = this.availableStatus[newIndex];
            }

        }
}
</script>
<style>
    .pointer {
        cursor: pointer;
    }
</style>