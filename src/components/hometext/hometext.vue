<template>
  <div class="content">
    <div class="title">
      <img class="logo" src="static/img/logo.png">
      <div class="description">{{ this.title }}</div>
    </div>
    <div class="links">
      <a v-for="(link,index) in this.links" :key="index" :href="link[1]">
        <i v-if="link[2]" class="fa" aria-hidden="true" :class="link[2]"></i>
        {{ link[0] }}
      </a>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import '../../common/css/font-awesome.css'
  export default {
    name: 'hometext',
    props: ['title', 'links']
  }
</script>

<style type="text/css">
  .content {
    text-align: center;
    z-index: 100;
    margin-bottom: 15vh;
    margin-bottom: 15vh;
  }

  .title {
    font-size: 84px;
    margin-top: 0px;
    margin-bottom: 0px;
  }

  .logo {
    width: 120px !important;
  }

  .description {
    margin-top: 30px;
    margin-bottom: 50px;
    font-size: 24px;
    font-weight: bold;
  }

  .links {
    margin-bottom: 50px;
  }

  .links > a {
    color: #9caebf;
    padding: 0 25px;
    font-size: 14px;
    font-weight: 600;
    letter-spacing: .1rem;
    text-decoration: none;
    text-transform: uppercase;
    line-height: 50px;
  }

  .links > a:hover {
    color: #52697f;
  }

</style>
