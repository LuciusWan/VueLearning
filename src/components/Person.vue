<template>
  <div class="person">
    <h2>姓名{{name}}</h2>
    <h2>年龄{{age}}</h2>
    <button @click="click">展示联系方式</button>
    <button @click="changeName">改变名称</button>
    <button @click="changeAge">改变年龄</button>

  </div>
</template>
<script>
  export default {
    name: "PersonInfo",
    data() {
      return {
        name:'张三',
        age:19,
        tel:'46546161626'
      }
    },
    methods:{
      click(){
        alert(this.tel)
      },
      changeName(){
        this.name='李四'
      },
      changeAge(){
        this.age +=1
      }
    }
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
