<script setup>
import { ref } from 'vue'
import { sayHello } from '../api/hello'
const count = ref(0);
const message = ref('zz—music-admin')

const hi = () => {
  sayHello().then(res => {
    console.log(res)
  })
  message.value = '一起'
}
</script>

<template>
  <h1>{{message}}</h1>
  <div>
    <q-btn
      color="primary"
      label="Primary"
      @click="count++"
    >点击此时{{count}}</q-btn>
    <q-btn
      color="primary"
      label="Primary"
      @click="hi"
    >点击提交{{count}}</q-btn>

  </div>
</template>
<style scoped>
a {
  color: #42b983;
}
</style>
