<template>
  <div class="person">
    <h2>姓名{{name}}</h2>
    <h2>年龄{{age}}</h2>
    <button @click="click">展示联系方式</button>
    <button @click="changeName">改变名称</button>
    <button @click="changeAge">改变年龄</button>

  </div>
</template>
<!--这个script用来标注这个组件名称是什么,如果没有的话就按文件名来看-->
<script>
export default {
  name: "PersonInfo",
}
</script>
<!--直接使用<script setup>可以不用写return-->
<script setup>
//使用setup可以让data和function放在一块,同时不允许用this,this在setup里面是unsigned
let name='张三'//数据不是响应式的,更改了不能在前端直接看到
let age=18
let tel='46616116'
function changeName(){
  name='李四'//name改变了,但name不是响应式
  console.log(name)
}
function changeAge(){
  age+=1//age改变了,但age不是响应式
  console.log(age)
}
function click(){
  alert("联系方式"+tel)
}
</script>
<style>
.person{
  background-color:skyblue; ;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
</style>
