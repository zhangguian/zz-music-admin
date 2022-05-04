<template>
  <div class="Login-page">
    <q-card>
      <q-card-section>
        <div class="title">欢迎登录ANJING-MUSIC</div>
        <q-form @submit="onSubmit" @reset="onReset" class="form">
          <q-input
            v-model="name"
            label="用户名"
            lazy-rules
            outlined
            :rules="[(val) => (val && val.length > 0) || '请输入用户名']"
          />

          <q-input
            type="password"
            v-model="age"
            label="密码"
            lazy-rules
            outlined
            :rules="[(val) => (val !== null && val !== '') || '请输入密码']"
          />

          <q-toggle v-model="accept" label="记住我" />

          <div class="submit">
            <q-btn
              class="full-width"
              label="登录"
              type="submit"
              color="primary"
            />
          </div>
        </q-form>
      </q-card-section>
    </q-card>
  </div>
</template>

<script setup>
  import { useQuasar } from "quasar";
  import { ref } from "vue";
  const name = ref(null);
  const age = ref(null);
  const accept = ref(false);
  const $q = useQuasar();
  const onSubmit = () => {
    if (accept.value !== true) {
      $q.notify({
        color: "red-5",
        textColor: "white",
        icon: "warning",
        message: "You need to accept the license and terms first",
      });
    } else {
      $q.notify({
        color: "green-4",
        textColor: "white",
        icon: "cloud_done",
        message: "Submitted",
      });
    }
  };

  const onReset = () => {
    name.value = null;
    age.value = null;
    accept.value = false;
  };
</script>

<style scoped lang="less">
  .Login-page {
    width: 100vw;
    height: 100vh;
    flex-direction: column;
    display: flex;
    justify-content: center;
    align-items: center;
    .title {
      margin: 4px auto;
      padding: 20px;
      font-size: 24px;
      text-align: center;
    }
    .form {
      width: 400px;
      .submit {
        width: 100%;
        padding: 10px 0px;
        text-align: center;
      }
    }
  }
</style>
