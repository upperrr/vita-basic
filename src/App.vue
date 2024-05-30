<template>
  <div>
    {{rawHtml}}
  </div>
  <div>
    {{rawHtml2}}
  </div>
  <h1 v-html="rawHtml2"></h1>

 <!--함축형 사용하면 아래와 똑같다 -->
  <h2 v-bind:class="{active: isActive}">클래스 바인딩 테스트 클래스</h2>   
  <h2 :class="{active: isActive}">클래스 바인딩 테스트 클래스</h2>
  <button @click="change">버튼</button> 

  <h3 style="color: orange; font-size: 24px;">스타일 바인딩 테스트</h3>
  <!-- vue.js style binding -->
  <h3 :style="{color: contColor, fontSize: fontSize + 'px'}">스타일 바인딩 테스트</h3>
</template>

<script>
export default {
  data () {
    return {
      rawHtml: '이것은 텍스트입니다',
      rawHtml2: '<span style="color: red">이것은 발간색 이어야 함</span>',
      isActive: false, //default 값은 뭘로 시작해도 상관 없다. 
      contColor: '#888888',
      fontSize: 48,
    }
  },
  methods: {
    change() {
      this.isActive = !this.isActive
      console.log('Button clicked!');
    },
  },
}
</script>

<style scoped>
h2.active {
  color: green;
}
</style>