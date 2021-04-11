<template>
  <div class="container">
    <p>{{ errorMessage }}</p>
    <div class="item">
      <input type="text" name="title" v-model="inputTitle" />
    </div>
    <div class="item">
      <input type="text" name="period" v-model="inputPeriod" />
    </div>
    <div class="item">
      <textarea
        name="detail"
        id
        cols="30"
        rows="10"
        v-model="inputDetail"
      ></textarea>
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
      errorMessage: "",
    };
  },
  methods: {
    async createTask() {
      if (this.inputTitle === "") {
        this.errorMessage = "タイトルを入力してください";
        return;
      }
      let result; // 成功した場合と失敗した場合の両方でresultを扱うことができるようにするためletを使用
      try {
        result = await api.post("/tasks", {
          title: this.inputTitle,
          period: this.inputPeriod,
          detail: this.inputDetail,
        });
        console.log(result);
      } catch (err) {
        this.errorMessage = "サーバーでエラーが発生しました";
        return;
      }
      this.errorMessage = "";
    },
  },
};
</script>

<style lang="scss"></style>
