<template>
    <div class="person">
      <h2>汽车信息：一台{{ car.brand }}汽车，价值{{ car.price }}万</h2>
      <button @click="changCarBrand">修改汽车品牌</button>
      <button @click="changCarPrice">修改汽车价格</button>
      <hr>
      <h2>游戏列表：</h2>
      <ul>
        <li v-for="g in games" :key="g.id"> {{ g.name }}</li>
      </ul>
      
      <button @click="changGamename">修改游戏名称</button>
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
  import { reactive } from 'vue'
    //  数据，原来是写在data中的，此时的name、age、tel都不是响应式的数据
  let car = reactive({brand: '奔驰', price: 100})
  let games = reactive([
    { id: 'sddsks01', name: '王者荣耀' },
    { id: 'sddsks02', name: '原神' },
    { id: 'sddsks03', name: '和平精英' },

  ])
  
  function changCarBrand(){
    car.brand = '宝马-运动款'
  }

  function changCarPrice(){
    car.price += 10
  }

  function changGamename(){
    games[2].name = '暴力摩托'
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