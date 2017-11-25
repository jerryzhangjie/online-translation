<template>
  <div id="app">
    <h2>在线翻译</h2>
    <translationForm v-on:translate="translated"></translationForm>
    <translationOutput v-bind:showtext="translatedtext"></translationOutput>
  </div>
</template>

<script>
import TranslationForm from './components/translationForm'
import TranslationOutput from './components/translationOutput'
export default {
  name: 'app',
  data() {
    return {
      translatedtext: ''
    }
  },
  components: {
    TranslationForm, TranslationOutput
  },
  methods: {
    translated(text, language) {
      //alert(text)
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20171028T130152Z.9bd7ef5e0e77c33a.df81ee1cdcabcc7068492afa3592e68f53e9de5f&lang='+ language+'&text='+text)
      .then((response)=>{this.translatedtext = response.body.text[0]})
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
