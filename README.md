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

## 构建你的主页
- ### 替换文本
  - 在**src/App.vue**文件中替换data的内容为你想要的值

    - `title`: 标题
    - `links`: 链接列表，每一个链接为一个字符串数组，数组第一个是显示的内容，第二个是链接
    - `myWebSite`: 本站地址
    - `ICP`: 网站备案号，没有可忽略

- ### 替换logo以及背景图片
  - 替换**static/img**里面的相应内容

- **替换以后需要重新build**
