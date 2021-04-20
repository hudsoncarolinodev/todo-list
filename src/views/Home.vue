<template>
  <div class="home">
    <div class="app_content">
      <h2>Adicionar novas tarefa</h2>
      <FormularioAdicionarTarefa @newTask = "pushNewTask($event)" />
      <h3>Lista de tarefas</h3>
      <ListaTarefas v-bind:newListTasks="listTasks" />
    </div>
   
    <div class="app_content">
      <h2>Tarefas concluidas</h2>
      <FormListaTarefasConcluidasulario />
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
      listTasks:[]
    }
  },
  methods:{
    pushNewTask(newTask){
      this.listTasks.push(newTask)
    }
  }
}
</script>
