<template>
    <div>
  <!-- 조건에 따라 렌더링을 시킨다. 전환 비용이 듬 -->
      <!-- <div v-if="isVisible" class="red"></div>
      <div v-if="isVisible==true" class="blue"></div>
      <div v-else class="black"></div> -->
  
  <!-- count를 바인딩 하여 동작 시켜 보자 -->
      <!-- <div v-if="count > 1" class="red"></div>
      <div v-else class="blue"></div>
  
      <button @click="count++">증가</button>
      <button @click="count--">감소</button> -->
  
  <!-- * 조건부 랜더링 : v-if와 다른점은 red div가 화면에 보이진 않지만 render는 된다는 것.-->
  <!-- v-show는 항상 렌더링 되어 DOM에 남아있다. display:none으로 render될 뿐이다. -->
  <!-- 전환 비용은 없지만, 초기 렌더링 비용이 더 높다 -->
      <div v-show="isVisible" class="red"></div>
      <div v-show="!isVisible" class="blue"></div>
      <div v-if="isVisible" class="black"></div>
    </div>
  </template>
  
  <script>
  export default {
    data () {
  
      return {
        isVisible: false,
        count: 0,
      }
    },
  }
  </script>
  
  <style scoped>
  .red {
    width: 100px;
    height: 100px;
  
    background-color: red;
  }
  .blue {
    width: 100px;
    height: 100px;
  
    background-color: blue;
  }
  .black {
    width: 100px;
    height: 100px;
  
    background-color: black;
  }
  </style>