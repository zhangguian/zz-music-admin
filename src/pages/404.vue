<template>
  <div class="nofind-page">
    <div class="error-code">404</div>
    <div class="tips">抱歉!当前页面不存在...</div>
    <div class="btn-group">
      <q-btn
        push
        color="primary"
        label="返回"
        @click="
          () => {
            $router.back();
          }
        "
      />
      <q-btn
        push
        color="white"
        text-color="primary"
        label="首页"
        @click="
          () => {
            $router.push('/');
          }
        "
      />
    </div>
  </div>
</template>

<script setup>
  import { ref } from "vue";
</script>

<style scoped lang="less">
  .nofind-page {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .error-code {
      font-size: 280px;
      line-height: 300px;
    }
    .tips {
      font-size: 20px;
      color: #bcb6b6;
      margin-bottom: 40px;
    }
    .btn-group {
      width: 200px;
      display: flex;
      flex-direction: row;
      justify-content: space-evenly;
      align-items: center;
    }
  }
</style>
