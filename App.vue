<template>
  <div id="app">
    <!--直接使用插值方式-->
    <p>{{msg}}</p>
    <!--使用v-text等同于插值-->
    <div v-text="msg"></div>
    <!--使用v-bind绑定title属性-->
    <div v-bind:title="title">将鼠标悬停在上面</div>
    <!--使用v-html-->
    <div v-html="h1"></div>
    <!--绑定src属性-->
    <img :src="url"/>
    <div :class="{'red':flag,'blue':!flag}">这是一个div标签</div>
    <!--循环数据，第一个高亮-->
    <ul>
      <li v-for="(item,key) in list" :key="key" :class="{'red':key==0,'blue':key==1}">
        {{key}}----{{item}}
      </li>
    </ul>
    <div class="box" :style="{width:boxWidth+'px'}"></div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    // data: {
    //   msg: '这是一个段落',
    //   title: '悬停后出现内容',
    //   h1: '<h1>这是一个一级标题</h1>'
    // }
    data () {
      return {
        msg: '这是一个段落',
        title: '悬停后出现内容',
        h1: '<h1>这是一个一级标题</h1>',
        url: require('./assets/logo.png'),
        flag: false,
        list: ['111', '222', '333'],
        boxWidth: 200
      }
    }
  }
</script>

<style>
  .red {
    color: red;
  }

  .blue {
    color: blue;
  }

  .box {
    width: 100px;
    height: 100px;
    background-color: red;
  }
</style>
