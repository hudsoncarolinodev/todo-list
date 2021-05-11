<template>
  <ul>
    <li v-for="(newTask, index) in newListTasks" :key="newTask.name">
        <span @click="deleteTask(index)">X</span>
        <h1>{{newTask.name}}</h1>
        <p>{{newTask.descripition}}</p>
        <button @click="concluirTask(index,newTask)">Concluir</button>
    </li>
</ul>
</template>

<script>
export default {
  props:['newListTasks'],
 
  methods:{
     deleteTask(index){
         this.$emit("deleteTask",index)
     },
      concluirTask(index,task){
        this.$emit("taskConcluida",task)
        this.$emit("deleteTaskConcluida",index)
     }

  },
   watch:{
        newListTasks(){
          this.listTasks = this.newListTasks
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
