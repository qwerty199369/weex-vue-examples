<template>
  <scroller class="wrapper">
    <div class="header" @click="openURL('https://www.w3.org/TR/css-flexbox-1/#align-content-property')">
      <text class="title">align-content</text>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: flex-start;</text>
      <div class="container row" style="align-content:flex-start;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: flex-end;</text>
      <div class="container row" style="align-content:flex-end;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: center;</text>
      <div class="container row" style="align-content:center;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: space-between;</text>
      <div class="container row" style="align-content:space-between;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: space-around;</text>
      <div class="container row" style="align-content:space-around;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">align-content: stretch;</text>
      <div class="container row" style="align-content:stretch;">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
        <div class="box E"><text class="label">E</text></div>
        <div class="box F"><text class="label">F</text></div>
        <div class="box G"><text class="label">G</text></div>
      </div>
    </div>
  </scroller>
</template>

<style scoped>
  .header {
    height: 120px;
    background-color: #00B4FF;
    justify-content: center;
    margin-bottom: 60px;
  }
  .title {
    font-size: 50px;
    text-align: center;
    color: #ffffff;
    font-family: monospace;
  }
  .row {
    flex-direction: row;
    flex-wrap: wrap;
  }
  .example-panel {
    align-items: center;
    margin-bottom: 50px;
  }
  .tips {
    font-size: 30px;
    color: #888888;
    padding-bottom: 10px;
    font-family: monospace;
  }
  .container {
    border-width: 2px;
    border-style: solid;
    border-color: #888888;
    width: 600px;
    height: 350px;
  }
  .box {
    /* height: 120px; */
    justify-content: center;
    align-items: center;
  }
  .A {
    width: 120px;
    background-color: #ff7070;
  }
  .B {
    width: 80px;
    background-color: #66b966;
  }
  .C {
    width: 180px;
    background-color: #519fff;
  }
  .D {
    width: 120px;
    background-color: #ffb37d;
  }
  .E {
    width: 150px;
    background-color: #c477ff;
  }
  .F {
    width: 100px;
    background-color: #67d9fb;
  }
  .G {
    width: 120px;
    background-color: #dcde64;
  }
  .label {
    padding-top: 20px;
    padding-bottom: 20px;
    font-size: 66px;
    color: #FFF;
  }
</style>

<script>
  const navigator = weex.requireModule('navigator')
  const storage = weex.requireModule('storage')
  export default {
    methods: {
      openURL (url) {
        const hash = 'ab57ab447248c35115144736ba38521a'
        const link = WXEnvironment.platform === 'Web'
          ? `http://dotwe.org/raw/htmlVue/${hash}`
          : `http://dotwe.org/raw/dist/${hash}.bundle.wx`
        storage.setItem('CURRENT_DOCUMENT_URL', url)
        navigator.push({ url: `${link}?_wx_tpl=${link}` })
      }
    }
  }
</script>
