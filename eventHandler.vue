<template>
    <div>
      <!-- 인라인 핸들러(v-click) 사용 -->
      <button v-on:click="count++">인라인 핸들러</button>
      <h1> {{ count }}</h1> <!-- 텍스트 보간법 호출 -->
  
      <!-- 메서드 핸들러 -->
      <button v-on:click="changeName">메서드 핸들러</button>
      <h1> {{ name }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    data () {
      
      return {
        count: 0,
        name: 'Vue.js',
      }
    },
      methods: {
        changeName() {
          this.name = '변경된 텍스트 데이터 입니다.'
        },
      },
  }
  </script>
  
  <style scoped>
  
  </style>