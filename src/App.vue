<template>
  <div>
    <h1>{{ text }}</h1>
    <h1>changeText 함수 호출 값: {{ changeText() }}</h1>
    <h1>changeText 함수 호출 값: {{ changeText() }}</h1>
    <h1>changeText 함수 호출 값: {{ changeText() }}</h1>

    <h2>{{ computedText }}</h2>
    <h2>{{ computedText }}</h2>
    <h2>{{ computedText }}</h2>
  </div>
</template>

<script>
export default {
  data () {
    
    return {
      text: 'Computed 테스트 데이터',
    }
  },
  // computed : 모양은 함수 이지만 data 취급을 합니다.
  // method 부분에 선언된 함수와 동일한 로직일 때
  // 캐싱 기능이 없는 methods는 호출될 때마다 console 값이 출력 되었습니다.
  // 반면에 computed는 캐싱 기능이 없기 때문에 methods와 어떤 차이점이 있는지
  // 한번 주의깊게 살펴보는 것이 포인트 입니다.
  computed: {
    computedText() {
      console.log('Computed 기능을 생성하였습니다.')
      return this.text.split("").reverse().join('')
    },
  },
  methods: {
    changeText() {
      console.log("함수 호출");
      console.log(this.text);

      return this.text.split("").reverse().join('')
    },
  }
}
</script>

<style scoped>

</style>