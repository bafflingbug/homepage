 <template>
  <div id="app" class="main">
    <v-background></v-background>
    <v-hometext></v-hometext>
    <v-info></v-info>
  </div>
</template>

<script type="text/ecmascript-6">
  import background from 'components/background/background.vue'
  import hometext from 'components/hometext/hometext.vue'
  import info from 'components/infobar/infobar.vue'
  export default {
    data: function () {
      return {
        title: '莫名其妙DeBUG',
        links: [
          ['BLOG', 'https://blog.bafflingbug.cn/'],
          ['TIEBASIGN', 'https://yun.bafflingbug.cn/'],
          ['ZHIHU', 'https://www.zhihu.com/people/godInZHIHU/'],
          ['GITHUB', 'https://github.com/bafflingbug/'],
          ['GITEE', 'https://gitee.com/bafflingbug/'],
          ['MAIL', 'Mailto:i@bafflingbug.cn']
        ],
        myWebSite: 'https://www.bafflingbug.cn/',
        ICP: '京ICP备16026454号'
      }
    },
    components: {
      'v-background': background,
      'v-hometext': hometext,
      'v-info': info
    }
  }
</script>

<style>
  .main {
    background-color: #14407E;
    background-image: url("../static/img/bg.png");
    background-repeat: repeat;
    background-position: center center;
    background-size: cover;
    color: #6289ad;
    font-family: 'Raleway';
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
