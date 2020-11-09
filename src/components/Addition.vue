<template>
  <div>
    <!-- <h3>当前最新的count值为：{{ $store.state.count }}</h3> -->
    <h3>{{ $store.getters.showNum }}</h3>
    <button @click="btnHandle1">+1</button>
    <button @click="btnHandle2">+N</button>
    <button @click="btnHandle3">+1 Async</button>
    <button @click="btnHandle4">+N Async</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    btnHandle1() {
      // commit 的作用就是调用某个 mutations 函数
      this.$store.commit("add");
    },

    btnHandle2() {
      this.$store.commit("addN", 3);
    },

    // 异步地让 count 自增 +1
    btnHandle3() {
      // 这里的 diapatch 函数专门用来触发 actions
      this.$store.dispatch("addAsync");
    },

    btnHandle4() {
      this.$store.dispatch("addNAsync", 5);
    },
  },
};
</script>

<style scoped></style>
