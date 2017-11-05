<template>
  <div id="background" class="background" ref="background">
  </div>
</template>

<script type="text/ecmascript-6">
  import background from './background.js'
  export default {
    name: 'background',
    mounted: function () {
      background.background()
    }
  }
</script>


<style>
  .background {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0px;
    right: 0px;
    top: 0px;
    bottom: 0px;
  }
</style>

