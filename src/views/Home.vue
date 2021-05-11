<template>
  <div class="home">
    <div class="app_content">
      <h2>Adicionar novas tarefa</h2>
      <FormularioAdicionarTarefa @newTask = "pushNewTask($event)" />
      <h3>Lista de tarefas</h3>
      <ListaTarefas 
      v-bind:newListTasks="listTasks"  
      @taskConcluida = "taskConcluida($event)"
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
    }
  }
}
</script>
