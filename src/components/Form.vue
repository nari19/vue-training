<template>
  <div class="container">
    <div class="item">
      <input type="text" name="title" v-model="inputTitle" />
    </div>
    <div class="item">
      <input type="text" name="period" v-model="inputPeriod" />
    </div>
    <div class="item">
      <textarea name="detail" v-model="inputDetail"></textarea>
    </div>
    <div class="item">
      <button @click="createTask">作成</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputTitle: "",
      inputPeriod: "",
      inputDetail: "",
    };
  },
  methods: {
    createTask() {
      // タスクを作成する処理
    },
  },
};
</script>

<style lang="scss"></style>
