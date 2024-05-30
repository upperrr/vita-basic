<template>
  <div>
    <button @click="changeMessage">{{ message }}</button>
    <div>{{ watchMessage }}</div>
    
  </div>
</template>

<script>
export default {
  data () {
    
    return {
      message: "Watch 기능 테스트 Original 문구",
      watchMessage: ''
    }
  },
  // message가 변경되는 것을 지켜 보고 있다가 changeMessage가 동작 될 때 작동한다. 
  watch: {
    message() {
      // window.alert("message 변수에 담긴 데이터가 변경 되었습니다.")
      this.watchMessage = 'Watch 동작'

    },
  },
  methods: {
    changeMessage() {
      console.log('함수 호출');
      this.message = '변경된 message 데이터 입니다'
    },
  },
}
</script>

<style scoped>

</style>