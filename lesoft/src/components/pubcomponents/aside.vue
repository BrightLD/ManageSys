<template>
  <div>
    <el-menu
      default-active="1-4-1"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      :collapse="isCollapse"
      router
    >
      <!-- 员工管理 -->
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-menu"></i>
          <span slot="title">员工管理</span>
        </template>
        <el-menu-item index="1-1">添加员工</el-menu-item>
        <el-menu-item index="1-2">职位变更</el-menu-item>
        <el-submenu index="1-3">
          <span slot="title">员工详情</span>
          <el-menu-item index="1-3-1" class="three-padding">积分详情</el-menu-item>
          <el-menu-item index="1-3-2" class="three-padding">跟岗计划详情</el-menu-item>
          <el-menu-item index="1-3-3" class="three-padding">添加辅导员</el-menu-item>
        </el-submenu>
      </el-submenu>
      <!-- 薪资管理 -->
      <el-submenu index="2">
        <template slot="title">
          <i class="el-icon-share"></i>
          <span slot="title">薪资管理</span>
        </template>
        <el-menu-item index="2-1">薪资详情</el-menu-item>
        <el-menu-item index="2-2">薪资类别</el-menu-item>
        <el-menu-item index="2-3">薪资月份</el-menu-item>
      </el-submenu>
      <!-- 跟岗计划 -->
      <el-submenu index="3">
        <template slot="title">
          <i class="el-icon-printer"></i>
          <span slot="title">跟岗计划</span>
        </template>
        <el-submenu index="3-1">
          <span slot="title">跟岗类别</span>
          <el-menu-item index="3-1-1" class="three-padding">添加跟岗类别</el-menu-item>
        </el-submenu>
        <el-submenu index="3-2">
          <span slot="title">跟岗计划</span>
          <el-menu-item index="3-2-1" class="three-padding">跟岗计划详情</el-menu-item>
        </el-submenu>
      </el-submenu>
      <!-- 公告通知 -->
      <el-submenu index="4" style="margin-bottom:30px;">
        <template slot="title">
          <i class="el-icon-bell"></i>
          <span slot="title">公告通知</span>
        </template>
        <el-menu-item index="2-1">添加公告</el-menu-item>
        <el-menu-item index="2-2">公告详情</el-menu-item>
      </el-submenu>
    </el-menu>
  </div>
</template>
<style>
html,
body,
.container {
  width: 100%;
  height: 100%;
}
/* 调整三级菜单元素 */
.three-padding {
  padding-left: 90px !important;
  text-align: left !important;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  height: 100% !important;
}
</style>

<script>
import eventVue from "../../../eventvue.js";
export default {
  data() {
    return {
      isCollapse: true
    };
  },
  created: function() {
    this.changeCollapse();
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    changeCollapse: function() {
      eventVue.$on("myFun", status => {
        //这里最好用箭头函数，不然this指向有问题
        this.isCollapse = status;
      });
    }
  }
};
</script>