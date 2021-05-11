<template>
  <ul>
    <li v-for="(newTask, index) in listTasks" :key="newTask.name">
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
  data(){
      return{
          listTasks:[
            {
                name:"Taks Exemple",
                descripition:"Lorem ipsum dolor, sit amet consectetur adipisicing elit."
            }],
            
      }
  },
  methods:{
     deleteTask(index){
        this.listTasks.splice(index,1)
     },
      concluirTask(index,task){
        this.$emit("taskConcluida",task)
        this.listTasks.splice(index,1)
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
