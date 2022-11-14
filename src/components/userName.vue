<template>

 <div>
    <h1> Search </h1>
    <input type="text" v-model="input">
    
    
    <ul>
       <li v-for="(name, index) in filteredNames" v-bind:key="index">
         {{name}}
       </li>
    </ul>
 </div>


</template>

<script>
export default {
    name:"userName",
      data() {
        return {
          names: [
             'Parth',
             'Eduardo',
             'Edgar',
             'Max',
             'Chencho',
             'Demian',
             'Alexis',
             'Citlali',
             'Luz',
             'Carlos',
             'Parth'],
          input:''
    }
  },

     computed: {
     filteredNames() {
     return this.input !== '' ? this.names.filter(name => name.toLowerCase().includes(this.input.toLowerCase())) : ''
    }
  }
}


</script>

<style scoped>


h1{
  font-family: 
  sans-serif;
  font-size: 40px;
  background: blue;
  text-align: center;
  justify-content: center;
  background: green;
}
  


</style>