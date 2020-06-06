<template>
  <div id="app">
    <div class="row p-2 justify-content-center">
      <div class="col-lg-10 col-md-10 col-sm-10">
        <app-heading>
          <h4>Quotes Added</h4>
        </app-heading>
        <div class="progress">
          <div class="progress-bar" role="progressbar" :style="{width:quoteCount*10+'%'}" :aria-valuenow="quoteCount" aria-valuemin="0" aria-valuemax="10">{{quoteCount}}/10</div>
        </div>
      </div>
    </div>
    <app-add-quote></app-add-quote>
    
  </div>
</template>

<script>
import Heading from './components/Heading.vue'
import AddQuote from './components/AddQuote.vue'

export default {
  name: 'App',
  components: {
    appHeading : Heading,
    appAddQuote : AddQuote
  },
  data(){
    return{
      quoteCount : 7,
      quotes : []
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
