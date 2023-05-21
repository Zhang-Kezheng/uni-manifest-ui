<script >


import MainItem from "@/components/MainItem.vue";

export default {
  name: "AppIconConfig",
  components: {MainItem,},
  data(){
    return{
      manifest:{
        alwaysShowBeforeRender:true
      }
    }
  },
}
</script>

<template>
  <div>
    <el-space :size="30" direction="vertical" alignment="start" fill wrap style="width: 100%">
      <div>
        <el-row class="tab-Title">App启动界面配置</el-row>
        <el-row><span class="description">应用启动及splash封面图相关配置。启动图或界面的变更需云打包后生效。本地打包需另行在原生工程中配置</span></el-row>
      </div>
      <el-row class="second-Title">启动界面选项</el-row>
      <div>
        <el-row >
          <el-checkbox v-model="manifest.alwaysShowBeforeRender">等待首页渲染完毕后再关闭Splash图</el-checkbox>
        </el-row>
        <el-row>
          <a href="https://uniapp.dcloud.net.cn/tutorial/app-splashscreen.html#">详情</a>
        </el-row>
      </div>
      <el-row >
        <el-checkbox v-model="manifest.alwaysShowBeforeRender">启动界面等待雪花</el-checkbox>
      </el-row>
      <el-row class="second-Title">Android启动界面设置</el-row>
      <main-item title="Android启动界面样式">
        <template #body>
          <el-row style="align-items: center">
            <el-radio v-model="manifest.a" label="1" style="margin-right: 10px">通用启动界面</el-radio>
            <a style="line-height: 100% ;margin-right: 10px " href="https://uniapp.dcloud.net.cn/tutorial/app-splashscreen.html#common" >详情</a>
            <el-radio v-model="manifest.a" label="2">自定义启动图</el-radio>
          </el-row>
        </template>
      </main-item>
      <div>
        <el-row >
          <el-checkbox v-model="manifest.alwaysShowBeforeRender">使用原生隐私政策提示框</el-checkbox>
        </el-row>
        <el-row>
          <a href="https://uniapp.dcloud.net.cn/tutorial/app-splashscreen.html#">详情</a>
        </el-row>
      </div>
    </el-space>
  </div>
</template>

<style scoped>

</style>