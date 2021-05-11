<template>
    <div class="app_content__formulario">
        <input type="text" v-model="name" @keydown.enter="criarTask()" placeholder="Adicionar nova tarefa">
        <textarea placeholder="Descrição Tarefa" @keydown.enter="criarTask()" v-model="descripition" ></textarea>
        <button @click="criarTask()" >Adicionar</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            name: "",
            descripition: "",
        }
    },
    methods:{
        criarTask(){
            
            this.$emit("newTask", {
                name:this.name,
                descripition:this.descripition
            })
           this.name = ""
           this.descripition = ""
        },
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
