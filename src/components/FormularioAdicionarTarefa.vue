<template>
    <div class="app_content__formulario">
        <input type="text" placeholder="Adicionar nova tarefa">
        <textarea placeholder="Descrição Tarefa" ></textarea>
        <button @click="getTaskValidation()" >Adicionar</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            task:{},
        }
    },
    methods:{
        getNewTask(){

        },
        getTaskValidation(){
            const inputValue = this.$el.querySelector("input").value
            const textValue = this.$el.querySelector("textarea").value
            
            if(inputValue.trim() !== "" && textValue.trim() !== ""){
                this.task.name         = inputValue
                this.task.descripition = textValue
                this.limparInputs()
            }else{
                this.error()
            }
        },
        error(){
            console.log("error")
        },
        limparInputs(){
            this.$el.querySelector("input").value = ""
            this.$el.querySelector("textarea").value = ""
        },
    },
    watch:{
        task(novo){
            console.log(novo)
            
        }
    }

 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
