<template>
    <div>
        <div>{{ props.sendProps1 }}</div>
        <div>{{ props.sendProps2 }}</div>
        <div>{{ props.sendProps3.id }}</div>
        <div>{{ props.sendProps3.name }}</div>
    </div>
</template>

<script setup lang="ts">
import {toRefs} from 'vue'

// * Options API로 변경. 
// defineProps 내장 함수의 사용
// *script setup lang="ts" 의 사용
// *내부 export문은 전부 지움
interface Obj {
  id: number,
  name: string
}

// 1. 컴포지션API에서 타입 스크립트를 활용하는 방법
// 1-1. Prop 받은 데이터 형식에 맞게 타입을 지정해준다. 

// Prop 받은 데이터 이름 자체에 미리 선언해둔 타입을 설정해준다.
interface Props {
    sendProps1: String,
    sendProps2: Number,
    sendProps3: Object,  
}
// defineProps toRefs 내장함수를 통해 Prop받은 데이터를 활용하여 템플릿 부분에 호출하여 사용한다. 
const props = defineProps<Props>() //별도로 import 선언 없이도 사용이 가능 하다. 

//객체 분해를 통해 더 간편하게 활용 할 수 있도록 도와준다
const {sendProps1, sendProps2, sendProps3} = toRefs(props)

// export default {
//     props: {
//         sendProps1: String,
//         sendProps2: Number,
//         sendProps3: Object,
//     },
//     data () {
//         return {}
//     }
// }
</script>

<style  scoped>

</style>