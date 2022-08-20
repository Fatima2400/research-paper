<template>
    <!-- <h1>AddNew</h1> -->
    <div class="main">
       <form @submit="onSubmit"> 
           
           <div class="first">
               <div class="form-group">
    <label for="exampleFormControlInput1">Paper Title</label>
    <input type="text" v-model="publish" name="publish" class="form-control" id="Input1" placeholder="Data Science research paper">
  </div>
               <div class="form-group">
    <label for="exampleFormControlSelect1">Research Type</label>
    <select class="form-control" id="Select1">
      <option>Publish Paper </option>
      <option>2</option>
      <option>3</option>
      <option>4</option>
      <option>5</option>
    </select>
  </div>
  
           </div>

        <h4 class="auth">Author's Details</h4>
  <div  class="name form-group">
    <label for="AuthorName">Author's Name</label>
    <input v-model="name" name="name" type="text" class="form-control" id="Input2" placeholder="Name">
  </div> 
  <div class="second">
<div class="form-group">
    <label for="Author">Author</label>
    <select  class="form-control" id="Select2">
      <option>Faculty/Student</option>
      <option>Faculty</option>
      <option>Student</option>
      
    </select>
  </div>
  <div id="year1" class="form-group">
    <label for="year">Year</label>
    <input v-model="year" name="year" type="number" class="form-control" id="Input3" placeholder="Year">
  </div>
  </div>
  
  
  <div class="form-group">
    <label for="citations">Citations</label>
     <input type="text" class="form-control" id="Input4" placeholder="Lorem Ipsum">
  </div> 
   <div class="form-group">
    <label for="indexing">Indexing</label>
    <select v-model="indexing" name="indexing" class="form-control" id="Select5">
      <option>Indexing </option>
      <option>1 </option>
      <option>2</option>
      <option>3</option>
      <option>4</option>
      <option>5</option>
    </select>
  </div>
  <div class="form-group">
    <label for="journalName">Journal Name</label>
     <input v-model="journal" name="journal" type="text" class="form-control" id="Input4" placeholder="Lorem Ipsum">
  </div>

  <input class="sub" type="submit">
</form> 


    </div>
    
</template>
<script>
//import Reports from "./Reports.vue"
export default {
    name: 'AddNew',
    data(){
        return {
            publish:'',
            name:'',
            year:'',
            indexing:'',
            journal:'',
        }
    },
    methods:{
        onSubmit(e){
           
e.preventDefault();
if(!this.publish){
    alert('please add name')
    return
}

const newTask = {
    id: Math.floor(Math.random()*100000),
    publish:this.publish,
            name:this.name,
            year:this.year,
            indexing:this.indexing,
            journal:this.journal,
}
this.$emit('new-task', newTask)
this.publish='',
this.name='',
this.year='',
this.indexing='',
this.journal='';
        }
    }
    

}
</script>

<style>
.first{
   /* border: 2px solid black; */
   width: 65%;
    
}
 .second{
    display: flex;
    /* justify-content: space-evenly; */
    /* border: 2px solid black; */
}
#year1{
    margin-left: 4%;
    /* border: 2px solid yellow; */
    width: 25%;
}

 #Select2{
    padding: 6px 50px;
    font-weight: bold;
    background-color:#ccd6f6 ;
}
#Select1 {
    width: 50% ;
    height: 40px;
    font-weight: bold;
    background-color:#ccd6f6 ;
}
 #Input4 {
    width: 65%;
    /* height: 2%; */
   
    font-weight: bold;
    background-color:#ccd6f6 ;
}
#Input1, #Input3{
     width: 100%;
    /* height: 2%; */
   
    font-weight: bold;
    background-color:#ccd6f6 ;
}

#Input2{
    width: 65%;
    height: 2%;
    font-weight: bold;
    background-color:#ccd6f6
}
.main{
    /* border: 2px solid black; */
    width: 90%;
    margin-left: 3%;
}
#Select5{
    width: 65%;
    height: 2%;
    font-weight: bold;
    background-color:#ccd6f6
}
.form-group{
    margin-top: 1%;
}
.sub{
    padding: 7px 30px;
    background-color: red;
    color: white;
    margin-top: 2%;
    
}
.rep{
    margin-top: 3%;
}
.auth{
    margin-top: 3%;
}

</style>
