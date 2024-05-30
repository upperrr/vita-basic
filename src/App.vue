<template>
  <div>
<!-- 기존의 HTML 코드 작성 방식 -->
    <li>{{ sampleArray[0] }}</li>
    <li>{{ sampleArray[1] }}</li>
    <li>{{ sampleArray[2] }}</li>
    <li>{{ sampleArray[3] }}</li><hr/>

<!-- v-for directive를 사용해 보자: key필수(react와 동일) -->
    <li v-for="item in sampleArray" :key="'item'">{{ item }}</li><hr/>
    <li v-for="user in otherArray" :key="user.id">{{ user }}</li>
    <li v-for="user in otherArray" :key="user.id">{{ user.id }} / {{ user.name }}</li><hr/>

    <li v-for="(item, index) in sampleArray" :key="'item'" @click="openDialo(index)">{{ item }} / {{ index }}</li>
    <li v-for="(user, index) in otherArray" :key="user.id">{{ user.id }} / {{ user.name }} / {{ index }}</li>
  </div>
</template>

<script>
export default {
  data () {

    return {
      sampleArray: ['a', 'b', 'c', 'd'],
      otherArray: [
        {id: 0,  name: 'john'},
        {id: 1,  name: 'lim'},
        {id: 2,  name: 'lrr'},
        {id: 3,  name: 'dddf'},
      ]
    }
  },
}
</script>

<style lang="scss" scoped>

</style>