<template>
   <div class="tab">
       <div class="hed">
<h2 class="head">Research Reports</h2>
       </div>

       <!-- <div :key="task.id"  v-for="task in tasks" class="re">
           <h3>
{{task.name}}
           </h3>
       </div> -->
       
       <table class="table">
  <thead>
    <tr>
      <!-- <th scope="col">#</th> -->
      <th scope="col">Paper title</th>
      <th scope="col">Author</th>
      <th scope="col">Year</th>
      <th scope="col">Indexing </th>
      <th scope="col">Journal name</th>
    </tr>
  </thead>
  <tbody>
    <tr  :key="task.id"  v-for="task in tasks">
      <!-- <th scope="row">{{task.id}}</th> -->
      <td>{{task.publish}}</td>
      <td>{{task.name}}</td>
      <td>{{task.year}}</td>
      <td>{{task.indexing}}</td>
      <td>{{task.journal}}</td>
    </tr>
    
   
  </tbody>
</table>
       </div>
       
   
</template>
<script>
export default {
    name: 'Reports',
    props: {
        tasks: Array,
    }
}
</script>
<style>
.head{
   margin-top: 3%;
   color: white;
}
.tab{
    width: 95%;
    
    border-radius: 20pxpx;
     box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
}
.hed{
    /* border: 2px solid red; */
    /* width: fit-content; */
    margin-top: 5%;
    /* margin-left: 1%; */
    background-color: black;
}

</style>