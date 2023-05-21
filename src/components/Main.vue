<template>
  <div >
      <el-tabs :tab-position="'left'"  stretch>
          <el-tab-pane label="基础配置">
              <base-config/>
          </el-tab-pane>
          <el-tab-pane label="App图标配置">
              <app-icon-config/>
          </el-tab-pane>
          <el-tab-pane label="App启动界面配置">
            <splash-screen-config/>
          </el-tab-pane>
          <el-tab-pane label="App模块配置">Task</el-tab-pane>
      </el-tabs>
  </div>
</template>

<script>
import BaseConfig from "@/components/BaseConfig.vue";
import AppIconConfig from "@/components/AppIconConfig.vue";
import SplashScreenConfig from "@/components/SplashScreenConfig.vue";

export default {
  name: 'HelloWorld',
    components: {SplashScreenConfig, AppIconConfig, BaseConfig}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
