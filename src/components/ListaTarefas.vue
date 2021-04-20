<template>
  <ul>
    <li v-for="(newTask,i) in listTasks" v-bind:key="i">
        <span>X</span>
        <h1>{{newTask.name}}</h1>
        <p>{{newTask.name}}</p>
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
            }]
      }
  },
  methods:{
     limparLista(){
         this.$el.querySelectorAll("li").forEach(element => {
             element.remove()
         });
         console.log(this.$el.querySelectorAll("li"))
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
