<template>
    <div class="person">
      <h2>姓名：{{name}}</h2>
      <h2>年龄：{{age}}</h2>
      <h2>地址：{{address}}</h2>
      <button @click="changeName">修改名字</button>
      <button @click="changeAge">修改年龄</button>
      <button @click="showTel">查看联系方式</button>
    </div>
</template>

  
<script lang="ts" setup name="Person234">
  import { ref } from 'vue'
    //  数据，原来是写在data中的，此时的name、age、tel都不是响应式的数据
    let name = ref('张三')
    let age = ref(18)
    let tel = '13888888888'
    let address = '拉萨'
  
    // 方法
    function changeName() {
    // name不是响应式的，name.value是响应式的，所以如下代码并不会引起页面的更新。    
      // name = ref('李四')
      name.value = '李四'
    }
    function changeAge() {
      age.value += 1
    }
    function showTel() {
      alert(tel)
    }
</script>
  
<style scoped>
    .person {
      background-color: skyblue;
      box-shadow: 0 0 10px;
      border-radius: 10px;
      padding: 20px;
    }
    button {
      margin: 0 5px;
    }
</style>