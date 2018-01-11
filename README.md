# homepage

> bafflingBUG的个人主页

基于[Vue](https://vuejs.org/)构建

粒子效果基于[Three@0.56](https://threejs.org/)制作

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

## 如何使用
1. 前往[release](https://github.com/bafflingbug/homepage/releases)下载最新的已发布版本(v2.0+)
2. 修改`/api/config.json`
    - `title`: 网站标题
    - `links`: 链接列表:每一个链接为一个字符串数组,数组第一个是显示的内容,第二个是链接,第三个是图标的标签(使用[Font Awesome](http://fontawesome.io/))
    - `myWebSite`: 本站地址
    - `ICP`: 网站备案号，没有请保持默认
3. 替换`/static/img`中的`bg.XXXXX.png`、`logo.png`、`favicon.ico`
    - `bg.XXXXX.png`: 背景图片
    - `logo.png`: 网站图标
    - `favicon.ico`: 网站头像
4. 使用[nginx](http://nginx.org/)或[Apache](http://httpd.apache.org/)等架设服务器