<template>
  <div id="app" class="main">
    <v-background></v-background>
    <v-hometext :title="title" :links="links"></v-hometext>
    <v-info :title="title" :myWebSite="myWebSite" :ICP="ICP"></v-info>
  </div>
</template>

<script type="text/ecmascript-6">
  import background from 'components/background/background.vue'
  import hometext from 'components/hometext/hometext.vue'
  import info from 'components/infobar/infobar.vue'
  import axios from 'axios'
  export default {
    name: 'App',
    data: function () {
      return {
        title: null,
        links: null,
        myWebSite: null,
        ICP: null
      }
    },
    components: {
      'v-background': background,
      'v-hometext': hometext,
      'v-info': info
    },
    created: function () {
      let vdata = this.$data
      axios.get('/api/config.json?r=' + new Date().getTime()).then(function (res) {
        vdata.title = res.data.title
        vdata.links = res.data.links
        vdata.myWebSite = res.data.myWebSite
        vdata.ICP = res.data.ICP
        document.title = vdata.title
      })
    }
  }
</script>

<style>
  .main {
    background-color: #14407E;
    background-image: url("../static/img/bg.jpg");
    background-repeat: repeat;
    background-position: center center;
    background-size: cover;
    color: #6289ad;
    font-family: "Raleway";
    font-weight: 100;
    height: 100vh;
    margin: 0;
    overflow: hidden;
    align-items: center;
    display: flex;
    justify-content: center;
    position: relative;
  }
</style>
