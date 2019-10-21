<template>
  <div class="row">
     <app-quote v-bind:key="quote" v-for="(quote,index) in quotes" v-on:click.native="deleteQuoteExistig(index)">{{quote}} - {{index}}</app-quote>
 </div>

</template>

<script>

import Quote from './Quote.vue'

export default {
  props:['quotes'],
  components: {
     'app-quote': Quote
  },
  data: function() {
      return { test : 'adfas'}
  },
  methods: {
      deleteQuoteExistig(index)
      {
          this.$emit("deleteQuote", index);
      }
  }
}
</script>

<style>

</style>


// native allows to delete the compoenet and click on the component