<template>
  <div id="app" class="container">
    <!--顶部组件 -->
    <Header></Header>
    <router-view/>
    <!-- 滚动组件 -->
    <el-scrollbar style="height:100%;">
      <!-- 侧边栏组件 -->
      <Aside></Aside>
    </el-scrollbar>
  </div>
</template>

<script>
import Header from "./components/pubcomponents/header";
import Aside from "./components/pubcomponents/aside";
import "font-awesome/css/font-awesome.css";
export default {
  name: "App",
  components: {
    Header,
    Aside
  }
};
</script>

<style>
html,
body {
  width: 100%;
  height: 100%;
}
.container {
  width: 100%;
  height: 100%;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
