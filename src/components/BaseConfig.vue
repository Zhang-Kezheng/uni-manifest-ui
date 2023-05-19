<template>
  <div>
      <el-space :size="30" direction="vertical" alignment="start" fill wrap style="width: 100%">
          <div>
              <el-row class="title">基础配置</el-row>
              <el-row><a  href="" @click.prevent="this.aclick('https://uniapp.dcloud.net.cn/collocation/manifest')">配置指南</a> </el-row>
          </div>
          <div>
              <el-row>
                  <span class="description">uni-app应用标识(AppID)</span>
              </el-row>
              <el-row>
                  <a href="">DCloud AppID使用说明</a>
              </el-row>
              <el-input v-model="mainfest.AppID">
                  <template #append><el-button>去登录</el-button></template>
              </el-input>
          </div>
          <div>
              <el-row>
                  <span class="description">应用名称</span>
              </el-row>
              <el-row>
                 <span class="description">离线打包需另行配置：</span> <a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android?id=appName">Android配置</a>&nbsp;<a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios.html#%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0">ios配置</a>
              </el-row>
              <el-input v-model="mainfest.AppName">
              </el-input>
          </div>
          <div>
              <el-row>
                  <span class="description">应用描述</span>
              </el-row>
              <el-input v-model="mainfest.description">
              </el-input>
          </div>
          <div>
              <el-row>
                  <span class="description">应用版本名称</span>
              </el-row>
              <el-row>
                  <span class="description">升级时必须高于上一次设置的值。离线打包需另行配置：</span> <a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android.html#versioncode">Android配置</a>&nbsp;<a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios.html#%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0">ios配置</a>
              </el-row>
              <el-input v-model="mainfest.AppName">
              </el-input>
          </div>
          <div>
              <el-row>
                  <span class="description">应用版本号</span>
              </el-row>
              <el-row>
                  <span class="description">应用版本号,必须是整数;升级时必须高于上一次设置的值。离线打包需另行配置：</span> <a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android.html#versioncode">Android配置</a>&nbsp;<a href="https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios?id=%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC%E5%8F%B7">ios配置</a>
              </el-row>
              <el-input v-model="mainfest.AppName">
              </el-input>
          </div>
          <div>
              <el-row>
                  <span class="description">vue版本选择</span>
              </el-row>
              <el-select v-model="mainfest.vueVersion" style="width: 100%">
                  <el-option
                      v-for="item in vueOptions"
                      :key="item.value"
                      :label="item.label"
                      :value="item.value"
                  />
              </el-select>
          </div>
          <div>
              <el-row>
                  <span class="description">国际化</span>
              </el-row>
              <el-row>
                  <a href="https://uniapp.dcloud.net.cn/tutorial/i18n.html">参考文档</a>
              </el-row>
          </div>
          <div>
              <el-row>
                  <span class="description">默认语言</span>
              </el-row>
              <el-select v-model="mainfest.vueVersion" style="width: 100%">
                  <el-option
                      v-for="item in vueOptions"
                      :key="item.value"
                      :label="item.label"
                      :value="item.value"
                  />
              </el-select>
          </div>
          <div>
              <el-row>
                  <span class="description">默认回退语言</span>
              </el-row>
              <el-select v-model="mainfest.vueVersion" style="width: 100%">
                  <el-option
                      v-for="item in vueOptions"
                      :key="item.value"
                      :label="item.label"
                      :value="item.value"
                  />
              </el-select>
          </div>
      </el-space>
  </div>
</template>

<script>
export default {
    name: "BaseConfig",
    data(){
        return{
            mainfest:{
                AppID:"",
                AppName:"",
                description:""
            },
            vueOptions:[{label:2,value:2},{label:3,value:3}]
        }
    },
    methods:{
        aclick(url){
            console.log(url)
            window.java({
                request: url,
                persistent:false,
                onSuccess: function(response) {
                    alert("返回的数据:"+response);
                }
            })
        }
    }
}
</script>

<style scoped>
a {
    color: #1d31ff;
}
</style>
