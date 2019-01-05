<template>
  <div id="demo1">
    <input type="text" v-model="msg"/>
    <br/>
    {{msg}}
    <br/>
    <button @click="handleClick">获取视图中的文字</button>
    <button @click="handleBtn">更改视图中的文字</button>
    <hr/>

    <input type="text" ref="userInfo"/>
    <div ref="box">这是一段文字</div>
    <button v-on:click="getInputValue">获取第二个表单的数据</button>
  </div>
</template>

<script>
  export default {
    name: 'demo1',
    data () {
      return {
        msg: '这是一段文字'
      }
    },
    methods: {
      handleClick () {
        alert(this.msg)
      },
      handleBtn () {
        this.msg = '这是更改后的数据'
      },
      getInputValue () {
        alert(this.$refs.userInfo.value)
        this.$refs.box.style.backgroundColor = 'red'
      }
    }
  }
</script>

<style scoped>

</style>
