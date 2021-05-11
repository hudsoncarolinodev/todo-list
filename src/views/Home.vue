<template>
  <div class="home">
    <div class="app_content">
      <h2>Adicionar novas tarefa</h2>
      <FormularioAdicionarTarefa @newTask = "pushNewTask($event)" />
      <h3>Lista de tarefas</h3>
      <ListaTarefas 
      v-bind:newListTasks="listTasks"  
      @taskConcluida = "taskConcluida($event)"
      @deleteTask = "deleteTask($event)"
      @deleteTaskConcluida = "deleteTask($event)"
      />
    </div>
   
    <div class="app_content">
      <h2>Tarefas concluidas</h2>
      <FormListaTarefasConcluidasulario 
      v-bind:taskConcluidas="taskConcluidas" 
      @deleteTaskConcluida = "deletatTask($event)" />
    </div>
  </div>
</template>

<script>

import FormularioAdicionarTarefa from '../components/FormularioAdicionarTarefa';
import ListaTarefas from '../components/ListaTarefas';
import FormListaTarefasConcluidasulario from '../components/ListaTarefasConcluidas';

export default {
  components:{
    FormularioAdicionarTarefa,
    ListaTarefas,
    FormListaTarefasConcluidasulario
  },
  data(){
    return{
      listTasks:[],
      taskConcluidas:[]
    }
  },
  methods:{
    pushNewTask(newTask){
      this.listTasks.push(newTask)
    },
    taskConcluida(taskConcluida){
      this.taskConcluidas.push(taskConcluida)
    },
    deletatTask(i){
      this.taskConcluidas.splice(i,1)
    },
    deleteTask(i){
      this.listTasks.splice(i,1)
    }
  },
  watch:{
    listTasks:{
      deep: true,
      handler(){
        localStorage.setItem("listTasks", JSON.stringify(this.listTasks))
      }
    },
    taskConcluidas:{
       deep: true,
      handler(){
        localStorage.setItem("listTasksConsluidas", JSON.stringify(this.taskConcluidas))
      }
    }
  },
  created(){
    const jasonListTasks = localStorage.getItem("listTasks")
    const jasonListTasksConsluidas = localStorage.getItem("listTasksConsluidas")
    if(Array.isArray(JSON.parse(jasonListTasks))){
       this.listTasks =  JSON.parse(jasonListTasks)
    }else{
      this.listTasks  = []
    }

    if(Array.isArray(JSON.parse(jasonListTasksConsluidas))){
       this.taskConcluidas =  JSON.parse(jasonListTasksConsluidas)
    }else{
      this.taskConcluidas  = []
    }
   
  }
}
</script>
