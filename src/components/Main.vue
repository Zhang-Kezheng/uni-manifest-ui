<template>
  <div >
      <el-tabs :tab-position="'left'"  stretch>
          <el-tab-pane label="基础配置">
              <base-config/>
          </el-tab-pane>
          <el-tab-pane label="App图标配置">Config</el-tab-pane>
          <el-tab-pane label="App启动界面配置">Role</el-tab-pane>
          <el-tab-pane label="App模块配置">Task</el-tab-pane>
      </el-tabs>
  </div>
</template>

<script>
import BaseConfig from "@/components/BaseConfig.vue";

export default {
  name: 'HelloWorld',
    components: {BaseConfig}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
