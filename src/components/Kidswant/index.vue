<template>
  <div class='list'' v-for = 'todo in todos'>
    {{ todo.tex }}
  </div>
  <div class='button' v-show='ok'>
    {{buttonValue}}
  </div>
  <div v-else='ok'>123</div>
  <div class="form">
    <label for="name">姓名</label> <input type="text" id='name' v-model='name' debounce='2000' placeholder=""/><br/>
    <label for="gender">性别</label> <input type="radio"><input type="radio" v-model='gender' ><br/>
    <label for="intersting">兴趣</label> <input type="checkbox" v-model='name'><input type="checkbox" v-model='name'><input type="checkbox" v-model='name'><br/>
  </div>
  <div>{{name}}</div>
  <div>{{{inner}}}</div>
</template>

<script>
  export default {
    data () {
      return {
        ok: true,
        buttonValue: '立即购买',
        todos: [{tex: 'learn react'}, {tex: 'learn vue'}, {tex: 'learn jquery'}],
        name: '郑春华',
        gender: '男',
        intersting: 'code',
        inner: '<div><p>this is a p </p></div>'
      }
    }
  }
</script>
<style scoped>
  .form{
    width:100%;
    text-align:left;
    margin-left: 20px;
    border:1px solid red;
  }
  input{
    margin-left:10px;
  }
  #name{
    /*outline: none;*/
    border:none;
    text-indent: 10px;
    border-bottom: 1px solid #333;
    color: #666;
    font-size:18px;
  }
  .list{
    width: 100%;
    height: 100px;
    line-height: 100px;
    text-align: left;
    font-size: 30px;
    border-bottom: 2px solid red;
  }
  .button{
    position: fixed;
    bottom: 30px;
    /*margin: 0  30px;*/
    color: #FFF;
    width: 750px;
    /*min-width: 100%;*/
    max-width:750px;
    height: 100px;
    background: #f39;
    font-size: 30px;
    text-align: center;
    line-height: 100px;
  }
</style>