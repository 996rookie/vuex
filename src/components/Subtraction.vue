<template>
  <div>
    <!-- <h3>当前最新的count值为：{{ count }}</h3> -->
    <h3>{{ showNum }}</h3>
    <button @click="btnHandle1">-1</button>
    <button @click="btnHandle2">-N</button>
    <!-- <button @click="btnHandle3">-1 Async</button> -->
    <button @click="subAsync">-1 Async</button>
    <!-- <button @click="btnHandle4">-N Async</button> -->
    <button @click="subNAsync(5)">-N Async</button>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions, mapGetters } from "vuex";
export default {
  data() {
    return {};
  },
  computed: {
    ...mapState(["count"]),
    ...mapGetters(["showNum"]),
  },
  methods: {
    ...mapMutations(["sub", "subN"]),
    ...mapActions(["subAsync", "subNAsync"]),

    btnHandle1() {
      this.sub();
    },

    btnHandle2() {
      this.subN(3);
    },

    // btnHandle3() {
    //   this.subAsync();
    // },

    // btnHandle4() {
    //   this.subNAsync(5);
    // },
  },
};
</script>

<style scoped></style>
