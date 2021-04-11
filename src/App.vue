<template>
  <div id="app">
    <Header />
    <Form />
  </div>
</template>

<script>
import Header from "./components/Header";
import Form from "./components/Form";
export default {
  name: "App",
  components: {
    Header,
    Form,
  },
};
</script>

<style lang="scss"></style>
