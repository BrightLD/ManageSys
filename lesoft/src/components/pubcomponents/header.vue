<template>
  <div class="header">
    <a class="logo" :class="{animated:status}">
      <template v-if="!status">
        <b>
          <i class="fa fa-diamond"></i> Admin-Vue
        </b>
      </template>
      <template v-else>
        <b>
          <i class="fa fa-diamond"></i>
        </b>
      </template>
    </a>
    <a href="javascript:;" class="switch" @click="switchAside">
      <i class="fa" :class="[status ?dedent:indent]"></i>
    </a>
    <a  href="javascript:;" class="notice" >
      <i class="fa fa-bell-o"></i>
    </a>
  </div>
</template>
<script>
import eventVue from "../../../eventvue.js";
export default {
  data() {
    return {
      status: true, //用来控制aside的状态切换
      dedent: "fa-dedent",
      indent: "fa-indent"
    };
  },

  methods: {
    switchAside: function() {
      this.status = !this.status;
      eventVue.$emit("myFun", this.status);
    }
  }
};
</script>
<style scoped>
.header {
  width: 100%;
  height: 50px;
  box-shadow: 0 2px 3px hsla(0, 0%, 7%, 0.1), 0 0 0 1px hsla(0, 0%, 7%, 0.1);
}
.logo {
  display: block;
  float: left;
  width: 160px;
  line-height: 50px;
  font-size: 20px;
  padding: 0 20px;
}
.switch {
  display: block;
  float: left;
  color: #48576a;
  line-height: 50px;
  font-size: 20px;
  padding: 0 10px;
  cursor: pointer
}
.switch:hover{
  background: #f9f9f9
}
.notice {
  display: block;
  float: right;
  margin-right: 250px;
  font-size: 20px;
  line-height: 50px;
}
.animated {
  animation-duration: 0.2s;
  -webkit-animation-duration: 2s;
  width: 65px;
  padding: 0;
  line-height: 50px;
}
</style>


