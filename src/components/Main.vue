<template>
  <div>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <el-menu
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          @select="handleSelect"
        >
          <el-submenu index="basic">
            <template slot="title">基础</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-submenu>
          <el-submenu index="principle">
            <template slot="title">原理</template>
            <el-menu-item index="p-responsive"
              >响应式</el-menu-item
            >
            <el-menu-item index="p-compilation"
              >模板编译</el-menu-item
            >
            <el-menu-item index="p-life-cycle"
              >生命周期</el-menu-item
            >
            <el-menu-item index="p-virtual-dom"
              >虚拟DOM</el-menu-item
            >
          </el-submenu>
          <!-- <el-submenu index="basic">
            <template slot="title">API</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-submenu> -->
        </el-menu>
      </div>
      <div v-if="activeIndex === 'basic'">
        1
        <BaseVue>1</BaseVue>
      </div>
      <div v-if="activeIndex.includes('p-')">
        <Principle :selectType="activeIndex"></Principle>
      </div>
      <!-- <div v-if="activeIndex === 'basic'">
        <baseVue></baseVue>
      </div> -->
    </el-card>
  </div>
</template>

<script>
import BaseVue from "../components/base/index.vue"
import Principle from "../components/principle/index.vue"
export default {
  components: {
    BaseVue,
    Principle,
  },
  data() {
    return {
      activeIndex: "basic",
    }
  },
  methods: {
    handleSelect(key) {
      this.activeIndex = key
    },
  },
}
</script>

<style></style>
