<template>
  <div id="app">
    <app-quote-progress v-bind:quoteCount="quotes.length" v-bind:maxQuotes="maxQuotes"></app-quote-progress>
    <app-quote-new v-on:addedNew="createQuote($event)"></app-quote-new>
    <app-quote-grid v-bind:quotes="quotes" v-on:deleteQuote="deleteQuote($event)"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12">
        <div class="alert alert-info">Please click on add to create a new quote</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteProgress from './components/QuoteProgress.vue'
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      maxQuotes:10,
      quotes : ['A wonderful quote']
    }
  },
  components: {
    'app-quote-grid': QuoteGrid,
    'app-quote-new':NewQuote,
    'app-quote-progress': QuoteProgress
  },
  methods: {
    createQuote(newQuote){
        this.quotes.push(newQuote);
    },
    deleteQuote(index){
      this.quotes.splice(index,1);
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

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
