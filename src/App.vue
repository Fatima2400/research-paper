<script>
//import Header from "./components/Header.vue"
import AddNew from "./components/AddNew.vue";
import Reports from "./components/Reports.vue"
//import Charts from "./components/Charts.vue"

export default {
  name: 'App',
  components: {
    // Header,
    AddNew,
    Reports,
   
  },
 
  data(){
    return {
        tasks:[],
        
    }
},
methods:{
newTask(task){
this.tasks= [...this.tasks, task]

}
},
created(){
   this.tasks = [
       {id:1,
       publish: "U998989",
       name: "Viraj Lagad ",
       year: 2022,
indexing: 1,
journal:'Physics',
       },
       {id:2,
       publish: "U37878",
       name: "Anirudh Murali",
       year: 2023,
indexing: 2,
journal:'Data Science',
       }

   ]
   
}
}
</script>

<template>
  
   

    <div class="wrapper">
      <h3 class="hedd">Academic Research</h3>
      <!-- <Header  /> -->
      <AddNew @new-task='newTask'  />
     <div class="rep">
<Reports :tasks="tasks"/>
</div>


 
      
    </div>
  

  
</template>

<style>

.hedd{
 color: white;
 background-color: black;
  text-align: center;
}
</style>


