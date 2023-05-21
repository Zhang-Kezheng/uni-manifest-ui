<template>
  <div>
      <el-space :size="30" direction="vertical" alignment="start" fill wrap style="width: 100%">
          <div>
              <el-row class="tab-Title">基础配置</el-row>
              <el-row><a  href="https://uniapp.dcloud.net.cn/collocation/manifest">配置指南</a> </el-row>
          </div>
          <main-item title="uni-app应用标识(AppID)" description="<a href=''>DCloud AppID使用说明</a>">
              <template #body>
                  <file-select :url="mainfest.name" text="去登录"></file-select>
              </template>
          </main-item>
          <main-item title="应用名称" description="离线打包需另行配置： <a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android?id=appName'>Android配置</a>&nbsp;<a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios.html#%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0'>ios配置</a>">
              <template #body>
                  <el-input v-model="mainfest.name">
                  </el-input>
              </template>
          </main-item>
          <main-item title="应用描述">
              <template #body>
                  <el-input v-model="mainfest.description">
                  </el-input>
              </template>
          </main-item>
          <main-item title="应用版本名称" description="升级时必须高于上一次设置的值。离线打包需另行配置： <a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android.html#versioncode'>Android配置</a>&nbsp;<a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios.html#%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0'>ios配置</a>">
              <template #body>
                  <el-input v-model="mainfest.versionName">
                  </el-input>
              </template>
          </main-item>
          <main-item title="应用版本号" description="应用版本号,必须是整数;升级时必须高于上一次设置的值。离线打包需另行配置： <a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android.html#versioncode'>Android配置</a>&nbsp;<a href='https://nativesupport.dcloud.net.cn/AppDocs/usesdk/ios?id=%E9%85%8D%E7%BD%AE%E5%BA%94%E7%94%A8%E7%89%88%E6%9C%AC%E5%8F%B7'>ios配置</a>">
              <template #body>
                  <el-input v-model="mainfest.versionCode">
                  </el-input>
              </template>
          </main-item>
          <main-item title="Vue版本选择">
              <template #body>
                  <el-select v-model="mainfest.vueVersion" style="width: 100%">
                      <el-option
                          v-for="item in vueOptions"
                          :key="item.value"
                          :label="item.label"
                          :value="item.value"
                      />
                  </el-select>
              </template>
          </main-item>
          <main-item title="国际化" description=" <a href='https://uniapp.dcloud.net.cn/tutorial/i18n.html'>参考文档</a>">
          </main-item>
          <main-item title="默认语言">
              <template #body>
                  <el-select v-model="mainfest.locale" style="width: 100%">
                      <el-option
                          v-for="item in localeOptions"
                          :key="item.value"
                          :label="item.label"
                          :value="item.value"
                      />
                  </el-select>
              </template>
          </main-item>
          <main-item title="默认回退语言">
              <template #body>
                  <el-select v-model="mainfest.fallbackLocale" style="width: 100%">
                      <el-option
                          v-for="item in fallbackLocaleOptions"
                          :key="item.value"
                          :label="item.label"
                          :value="item.value"
                      />
                  </el-select>
              </template>
          </main-item>
      </el-space>
  </div>
</template>

<script>
import MainItem from "@/components/MainItem.vue";
import FileSelect from "@/components/FileSelect.vue";

export default {
    name: "BaseConfig",
    components: {FileSelect, MainItem},
    data(){
        return{
            mainfest:{
                name:"",
                appid:"",
                description:"",
                versionName : "1.0.0",
                versionCode : "100",
                locale:"",
                fallbackLocale:""

            },
            vueOptions:[{label:2,value:2},{label:3,value:3}],
            localeOptions:[
                {label:'跟随系统或宿主的语言配置(auto)',value:'auto'},
                {label:'英文(en)',value:'en'},
                {label:'中文简体(zh-Hans)',value:'zh-Hans'},
                {label:'中文繁体(zh-Hant)',value:'zh-Hant'},
                {label:'法语(fr)',value:'fr'},
                {label:'西班牙语(es)',value:'es'}
            ],
            fallbackLocaleOptions:[
                {label:'英文(en)',value:'en'},
                {label:'中文简体(zh-Hans)',value:'zh-Hans'},
                {label:'中文繁体(zh-Hant)',value:'zh-Hant'},
                {label:'法语(fr)',value:'fr'},
                {label:'西班牙语(es)',value:'es'}
            ]
        }
    },
    methods:{
    }
}
</script>

<style scoped>
</style>
