<template>

 <h2> Parent Component </h2>
 <h3>{{title}}</h3><hr>
 <input type="text" ref="name">
 <button @click="clickfunction">Click here</button><hr>

 <div v-if="showmodel">
   <Child  :header="header" :footer="footer" @close="show" >
   <hr><hr><h3>template sharing from parent to child using slot</h3><hr><hr>
   <h3>specifically mention slot </h3>
   <template v-slot:links>
     <a href="#">signup now </a>
   </template>
   </Child>
    </div>

    <h3>Using $emits (parent to child) </h3>
    <button @click="show">Showchild</button><hr><hr> 
 
 

 
</template>

<script>
import Child from './components/Child.vue'
export default {
  name: 'App',
  components: { Child },

  data(){
    return{
      title:"Access Text field by using Template $ref",
      header:"1st prop",
      footer:"2nd prop",
      showmodel:false
    }
  },
   methods:{
    clickfunction(){      
      console.log(this.$refs.name)
      
      this.$refs.name.focus()
    },
    show(){
      this.showmodel =! this.showmodel
    }
  }
    
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
