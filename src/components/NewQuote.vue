<template>
  <div class="row">
      <form>
  <div class="col-sm-8 col-sm-offset-2 form-group">
      <label>Quote</label>
      <textarea rows="3" v-model="quote"></textarea>
  </div>
  <div class="col-sm-8 col-sm-offset-2 form-group">
      <button class="btn btn-primary" v-on:click.prevent="createNew">Create New</button>
  </div>
  </form>
  </div>
</template>

<script>
export default {
  data: function(){
      return { quote : ''}
  },
  methods: {
      createNew()
      {
          this.$emit("addedNew",this.quote);
          this.quote ='';
      }
  }
}
</script>

<style>

</style>
