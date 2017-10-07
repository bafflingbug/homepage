<template>
  <div class="content">
    <div class="title">
      <img class="logo" src="./logo-b.png">
      <div class="description">{{ this.$parent.title }}</div>
    </div>
    <div class="links">
      <a v-for="link in this.$parent.links" :href="link[1]">
        {{ link[0] }}
      </a>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    name: 'hometext'
  }
</script>

<style type="text/css">
  .content {
    text-align: center;
    z-index: 100;
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
