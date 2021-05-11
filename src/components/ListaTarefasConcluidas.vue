<template>
    <ul>
        <li v-for="(newTask, index) in taskConcluidas" :key="newTask.name">
            <span @click="deleteTask(index)">X</span>
            <h1>{{newTask.name}}</h1>
            <p>{{newTask.descripition}}</p>
        </li>
    </ul>
</template>

<script>
    
export default {
    props:["taskConcluidas"],

    methods:{
        deleteTask(index){
            this.$emit("deleteTaskConcluida",index)
        },
        // concluirTask(index,task){
        //     this.$emit("taskConcluida",task)
        //     this.listTasks.splice(index,1)
        // }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
