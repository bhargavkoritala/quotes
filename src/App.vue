<template>
  <div class="container" id="app">
    <div class="row justify-content-center">
      <div class="col-lg-12 col-md-12 col-sm-12">
        <app-heading>
          <h4>Quotes Added</h4>
        </app-heading>
        <div class="progress">
          <div class="progress-bar" role="progressbar" :style="{width:quotes.length*10+'%'}" :aria-valuenow="quotes.length" aria-valuemin="0" aria-valuemax="10">{{quotes.length}}/10</div>
        </div>
      </div>
    </div>
    <app-add-quote @newQuote='includeNew'></app-add-quote>
    <app-quotes @del-quote='deleteQuote' :quotes="quotes"></app-quotes>
    <app-info>
      <div class="row justify-content-center">
        <div class="col-lg-12 col-md-12 col-sm-12">
          <p class="alert alert-primary">Info : Click on quote to delete it</p>
        </div>
      </div>
    </app-info>
  </div>
</template>

<script>
import Heading from './components/Heading.vue'
import AddQuote from './components/AddQuote.vue'
import Quotes from './components/Quotes.vue'
import Info from './components/Info.vue'
export default {
  name: 'App',
  components: {
    appHeading : Heading,
    appAddQuote : AddQuote,
    appQuotes : Quotes,
    appInfo : Info
  },
  data(){
    return{
      quotes : ['You only live once, but if you do it right, once is enough']
    }
  },
  methods:{
    includeNew(quoteAdded){
      if(this.quotes.length==10){
        alert('Delete a quote to add a new one !')
      }
      else{
         this.quotes.push(quoteAdded) 
      }
      
    },
    deleteQuote(delQuote){
      this.quotes = this.quotes.filter((quote)=>quote!=delQuote)
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
