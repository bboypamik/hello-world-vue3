<template>
  <h1>Hello-World</h1>
  <p v-once>My name is {{myName}} and my dog name is {{myDog}}</p>
  <button @click="helloWorld">click me yayayay</button>
  <p>{{myName}}</p>
</template>

<script>

export default {

  data(){
    return {
    myName: 'Miro',
    myDog: 'Mrvica'
    }
  },

  methods: {
    helloWorld(){
      alert('I am available')
    }
  },

  mounted(){
    this.myName ='tandom'
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
