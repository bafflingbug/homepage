<template>
  <div id="info" class="infobar">
    <span class="info">
      {{ this.text }}
      <a :href="this.$parent.myWebSite">{{ this.$parent.title }}</a>
      <span v-if="this.$parent.ICP"> | </span>
      <a v-if="this.$parent.ICP" href="http://www.miitbeian.gov.cn">{{ this.$parent.ICP }}</a>
    </span>
  </div>
</template>

<script>
  export default {
    name: 'info',
    data: function () {
      return {
        text: ''
      }
    },
    mounted: function () {
      let year = new Date().getFullYear()
      this.text = '© ' + year.toString() + ' Power by '
    }
  }
</script>

<style>
  .infobar {
    text-align: center;
    position: fixed;
    bottom: 2%;
    margin: auto;
    left: 0px;
    right: 0px;
    bottom: 2%;
  }

  .info {
    font-weight: 400;
    font-size: 14px;
    color: #9caebf;
  }

  .info > a {
    color: #9caebf;
    text-decoration: none;
  }

  .info > a:hover {
    color: #52697f;
  }
</style>
