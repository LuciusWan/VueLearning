<template>
  <div class="person">
<!--    这里的name不是name对象,而是自动改为了name.value-->
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
  import { ref } from 'vue'
  //通过ref把name和age变为了ref实现对象refImpl,如果需要变成响应式的数据就在外面包一层ref
  //ref会自动导包
  let name=ref('张三')
  let age=ref(18)
  let tel='46616116'
  console.log(name)
  console.log(age)
  function changeName(){
    name.value='李四'//name现在已经被封装为一个对象,让name对象的value属性变为目标值才能改变最终结果
    console.log(name)
  }
  function changeAge(){
    age.value+=1
    console.log(age)
  }
  function click(){
    alert("联系方式:"+tel)
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
