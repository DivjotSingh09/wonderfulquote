<template>
  <div class="col-sm-4">
  <div class="panel panel-default">
      <div class="panel-body quote">
          <slot></slot>
      </div>
  </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style>
.panel-body {
    font-family: "Arizonia", cursive;
    font-size: 24px;
}

.quote {
    cursor: pointer;
}

.quote:hover{
    background-color: palevioletred;
}
</style>
