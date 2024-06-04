<template>
  <div>
    <!-- v-bind를 생략해도 된다. 축약형 -->
    <!-- <ChildComponent v-bind:sendProps1="title" v-bind:sendProps2="createAt" v-bind:sendProps3="odj" /> -->
    <ChildComponent :sendProps1="title" :sendProps2="createAt" :sendProps3="obj" />
  </div>
</template>

<!-- composition api에서는 setup이라는 키워드가 반드시 필요하다 -->
<script setup lang="ts">
import ChildComponent from './components/ChildComponent.vue'
import { reactive, ref } from 'vue'

interface Obj {
  id: number,
  name: string
}

const title = ref<string>("부모컴포넌트에서 선언된 데이터")
const createAt = ref<number>(2024)
const obj = reactive<Obj>({
  id: 2024,
  name: 'John'
})

// export default {
//     components: {
//       ChildComponent,
//   },
//   data () {
//     return {
//       title: "부모컴포넌트에서 선언된 데이터",
//       createAt: 2024,
//       obj: {
//         id: 2024,
//         name: "john",
//       },
//     }
//   },
// }
</script>

<style lang="scss" scoped>

</style>