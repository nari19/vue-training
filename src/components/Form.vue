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
import api from "@/api";

export default {
  data() {
    return {
      inputTitle: "",
      inputPeriod: "",
      inputDetail: "",
    };
  },
  methods: {
    async createTask() {
      const result = await api.post("/tasks", {
        title: this.inputTitle,
        period: this.inputPeriod,
        detail: this.inputDetail,
      });
      console.log(result);
    },
  },
};
</script>

<style lang="scss"></style>
