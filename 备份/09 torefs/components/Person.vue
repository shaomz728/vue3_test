<template>
    <div class="person">
      <h2>姓名：{{ person.name }}</h2>
      <h2>年龄：{{ person.age }}</h2>
      <h2>性别：{{ person.gender }}</h2>
      <button @click="changName">修改姓名</button>
      <button @click="changAge">修改年龄</button>
    </div>
    
    <!-- //如下是对按钮进行单独的定义 -->
    <!-- <div class="person">
      <h2>汽车信息：一台{{ car.brand }}汽车，价值{{ car.price }}万</h2>
      <div class="group1">
        <button @click="changCarBrand">修改汽车品牌</button>
        <button @click="changCarPrice">修改汽车价格</button>
      </div>  
      <hr>
      <h2>游戏列表：</h2>
      <li v-for="g in games" :key="g.id"> {{ g.name }}</li>
      <div class="group2">
        <button @click="changGamename">修改游戏名称</button>
      </div>
    </div> -->
</template>

  
<script lang="ts" setup name="Person234">
  import { ref,reactive,toRef,toRefs } from 'vue'

  //源数据
  let person = reactive({name: '张三', age: 18, gender: '男'})

  // 通过toRefs将person对象中的n个属性批量取出，且依然保持响应式的能力
  let{name,age} = toRefs(person)  
  console.log(toRefs(person))
  
  // 方法
  function changName(){
    name.value += '~'
    console.log(name,person.name)
  }
  function changAge(){
    age.value += 1
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
      margin: 20px 5px;
      background-color: white;
    }
     /* 以下是分别定义按钮的格式 */
    /* .group1 button {
      margin: 5px;
      padding: 8px 16px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    .group1 button:hover {
    background-color: #0056b3;
    }
    .group2 button {
      margin: 5px;
      padding: 8px 16px;
      background-color: #d614c9;
      color: rgb(7, 239, 100);
      border: none;
      border-radius: 4px;
      cursor: pointer;
    } */
</style>