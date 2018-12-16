<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>这是一个山寨的翻译</h5>
    <translate-input v-on:formtranslate="translateText"></translate-input>
    <translate-output v-text="translatedText"></translate-output>
  </div>
</template>

<script>
//导入组件
import TranslateInput from './components/translateinput'
import TranslateOutput from './components/translateoutput'

export default {
  name: 'App',
  data:function(){
    return {
      translatedText: ""
    }
  },
  components:{
    TranslateInput,
    TranslateOutput
  },
  methods:{
    translateText:function(text,language){
        // console.log(text+','+language);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180802T072252Z.7fb2f98c9da21370.977ca030bf49a05272c581c24562ffbc22ec54ba&lang='+language+'&text='+text)
        .then((response) => {
          this.translatedText = response.body.text[0];
        })
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
