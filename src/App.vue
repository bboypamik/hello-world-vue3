<template>
  <h1>Speed Typer</h1>
  <p :value="score">Your Score: {{score}}  / {{keywords.length}}</p>
  <p>
    <span
      :class="{
      correct: keyword.correct,
      wrong: keyword.wrong,
      pending: keyword.pending
      }"
      v-for="keyword in keywords" :key="keyword.text">
      {{keyword.text}} {{' '}}
    </span>
  </p>
  <input type="text" :value="inputValue" @keyup.space="processInput($event)">
</template>

<script>

      const defaultKeywords = [

        'Race', 'is', 'part', 'of', 'everyday', 'life', 'in', 'the', 'United', 'States',
'asked', 'for', 'our', 'race', 'when', 'we', 'fill', 'out', 'forms', 'at', 'school', 
'work', 'when', 'we', 'visit', 'a', 'government', 'agency', 'or', 'doctor',
'office',' We', 'read', 'or', 'hear', 'about', 'race', 'in', 'the', 'daily', 'news',' and',
'it', 'comes', 'up', 'in', 'informal', 'discussions', 'in', 'our', 'neighborhoods',
'and', 'social', 'circles',' Most', 'of', 'us', 'can', 'apply','to', 'ourselves', 'and',
'the', 'people', 'around', 'us','labels', 'like', 'white', 'or', 'Asian',' Yet', 'for',
'all', 'its', 'familiarity',' race', 'is', 'strangely', 'difficult', 'to', 'define',' When',
'asked', 'people', 'to', 'explain', 'what', 'race', 'is', 'many', 'have', 'trouble', 'answering'

      ].map(keyword => {
        return{
          text: keyword,
          correct: false,
          wrong: false,
          pending: true
        }
      })
export default {

  data(){
    return {
      keywords: defaultKeywords,
      inputValue: "",
      index: 0,
      score: 0
  }

  },

  methods: {
    processInput(event){
      const value = event.target.value.trim()      
      if(value ===""){
        return;
      }
      if(this.keywords[this.index].text === value){
        // correct answer
        this.keywords[this.index].correct = true
        this.keywords[this.index].wrong = false
        this.keywords[this.index].pending = false
        this.score++
      }else{
        // wrong answer
        this.keywords[this.index].correct = false
        this.keywords[this.index].wrong = true
        this.keywords[this.index].pending = false
      }
      this.inputValue ="";
      this.index++;
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

.pending {
  font-weight: bold;
}

.correct {
  font-weight: bold;
  color: green;
}

.wrong{
  font-weight: bold;
  color: red;
}
</style>
