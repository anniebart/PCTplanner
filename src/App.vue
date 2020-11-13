<template>
  <div id="app">
    <MainHeader/>
  <h1>plan out your PCT route</h1>
    <h2>Plan by pace </h2>
    <form>
      <div>
      <input v-model='pace' type='number' id='pace' placeholder="average pace" min=1 max=100> miles per day
      </div>
      <button type='submit'>submit</button>
    </form>
    <p> your hike will take approximately {{checkTripLength()}} days </p>

     <h2>Plan by Trip Length </h2>
     <form>
      <div>
      <input v-model='tripLength' type='number' id='tripLength' placeholder="trip length" min=1 max=400>days
      </div>
      <button type='submit'>submit</button>
    </form>
    <p> your pace will need to be {{ checkPace() }} miles per day </p>

  </div>
</template>

<script>
import MainHeader from './components/MainHeader'
export default {
  name: 'App',
  components: {
    MainHeader,
  },
  data: function(){
    return {
      pace: Number,
      tripLength: Number,

    }
    
  },
  methods: {
    checkTripLength: function(){
      if (this.pace > 0){
      return  Math.floor(2650/this.pace) } else {return 0}
    },
    checkPace: function(){
      if (this.tripLength >0){
        return Math.floor(2650/this.tripLength)}
        else {
          return 0
        }
   
    }
  }
  // methods: {
  //   getTripLength: function(){

  //   }
  // }
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

input {
  width:100px;
}

</style>
