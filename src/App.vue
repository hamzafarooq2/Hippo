<template>
  <Header />
  <div class="main">
    <Sidebar />
    <Columns />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import Columns from "./components/Columns.vue";

export default {
  name: "App",
  components: {
    Header,
    Sidebar,
    Columns,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
.main {
  display: flex;
}
</style>
