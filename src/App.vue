<template>
  <div>
    <Header></Header>
    <router-view></router-view>
    <Footer v-show="$route.meta.show"></Footer>
  </div>
</template>

<script>
import Header from "./components/Header/index.vue";
import Footer from "./components/Footer/index.vue";
export default {
  name: "App",
  components: { Header, Footer },
  mounted() {
    // 通知Vuex发送请求，获取数据，存储于仓库中
    this.$store.dispatch("categoryList");
  },
};
</script>

<style>
</style>
