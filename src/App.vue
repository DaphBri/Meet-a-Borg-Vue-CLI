<template>

<div class="app">
  <header class="screen">
    <div class="txt-block">
      <div class="logos">
        <img class="logos__hart" src="@/assets/img/Love_Heart_symbol.svg.png" alt="heart">
        <img class="logos__flame" src="@/assets/img/tinder.svg" alt="flame">
      </div>
      <h1>MEET A 'BORG</h1>
      <p>Ça va pécho chez les robots 🤖🍆🍑</p>
    </div>     
    </header>

  <RobotFilter 
  v-bind:males="males"
  v-bind:females="females"
  @filterApp="filter($event)"
  />

  <RobotList 
  v-bind:filteredRobots="filteredRobots"
  
  />
  
</div>
</template>

<script>
import axios from "axios"
import RobotList from './components/RobotList.vue'
import RobotFilter from './components/RobotFilter.vue'

export default {
  name: 'app',

  components: {
    RobotFilter,
    RobotList
  },
  methods:{
    filter(type){
       console.log("filter in app")
      if(type==='Male'){
          this.filteredRobots = this.males;  //"filteredRobots" is defined in the index.html
      }
      else if(type === 'Female'){
          this.filteredRobots = this.females;
      }
      else{
          this.filteredRobots = this.allRobots;
      }
    }
  },

  data(){
        return {
            allRobots: [],
            filteredRobots: [],     //list, voir sous 'axios'
            males:[],               //list, voir sous 'axios'
            females:[],         
    }
  },

  created(){
  axios.get("https://wt-902485dbb4fca4fccee3a0efcde5b34c-0.sandbox.auth0-extend.com/robots")
    .then(response => {
        this.filteredRobots = response.data;                  //response data in axios, under #main!
        this.males = this.filteredRobots.filter(r => r.gender ==='Male');       //list, voir sous 'axios'
        this.females = this.filteredRobots.filter(r => r.gender ==='Female');   //list, voir sous 'axios'
        this.allRobots = this.filteredRobots;
    })
  },
  
}
</script>

<style lang="scss">
@import 'assets/css/style.min.css';
#app{

}
</style>
