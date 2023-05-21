<template>
  <div>
    <el-space :size="30" direction="vertical" alignment="start" fill wrap style="width: 100%">
      <div>
        <el-row class="tab-Title">App图标配置</el-row>
        <el-row><span class="description">IOS、Android应用图标配置。云打包后生效。本地打包需另行在原生工程中配置</span><a
            href="https://uniapp.dcloud.net.cn/tutorial/app-icons">应用图标配置注意事项</a></el-row>
      </div>
      <main-item title="自动生成图标" description="仅用于自动生成图标，建议使用1024x1024的图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
          <el-row>
            <el-checkbox v-model="auto">不替换手动设置的图标</el-checkbox>
            <el-button type="primary" size="default">自动生成所有图标并替换</el-button>
            <el-button type="primary" size="default">游览生成图标所在目录</el-button>
          </el-row>
        </template>
      </main-item>
      <el-row style="font-size: 20px">Android图标配置</el-row>
      <main-item title="72x72" description="hdpi高分屏应用图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="96x96" description="xhdpi 720P高分屏应用图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="144x144" description="xxhdpi 1080P高分屏程序图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="192x192" description="xxxhdpi 4k高分屏程序图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <el-row style="font-size: 20px">app store</el-row>
      <main-item title="提交app store使用的图标1024x1024" >
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <el-row style="font-size: 20px">iPhone图标配置</el-row>
      <main-item title="120x120" description="iOS7-11程序图标(iPhone4S/5/6/7/8)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="180x180" description="iOS7-11程序图标(iPhone6plus/7plus/8plus/X)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="80x80" description="iOS7-11 Spotlight(iPhone5/6/7/8)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="120x120" description="iOS7-11 Spotlight(iPhone6plus/7plus/8plus/X)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="58x58" description="iOS5-11 Settings设置图标(iPhone5/6/7/8)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="87x87" description="iOS5-11 Settings设置图标(iPhone6plus/7plus/8plus/X)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="40x40" description="iOS7-11 通知栏图标(iPhone5/6/7/8)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="60x60" description="iOS7-11 通知栏图标(iPhone6plus/7plus/8plus/X)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <el-row style="font-size: 20px">iPad图标配置</el-row>
      <main-item title="76x76" description="iOS7-11程序图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="152x152" description="iOS7-11程序图标(高分屏)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="167x167" description="iOS9-11 程序(iPad Pro)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="40x40" description="iOS7-11 Spotlight搜索图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="80x80" description="iOS7-11 Spotlight搜索图标(高分屏)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="29x29" description="iOS7-11 设置图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="58x58" description="iOS7-11 设置图标(高分屏)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="20x20" description="iOS7-11 通知栏图标">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
      <main-item title="40x40" description="iOS7-11 通知栏图标(高分屏)">
        <template #body>
          <file-select :url="mainfest.name" text="去游览"></file-select>
        </template>
      </main-item>
    </el-space>
  </div>
</template>

<script>
import MainItem from "@/components/MainItem.vue";
import FileSelect from "@/components/FileSelect.vue";

export default {
  name: "AppIconConfig",
  components: {FileSelect, MainItem},
  data() {
    return {
      mainfest: {
        name: "",
        appid: "",
        description: "",
        versionName: "1.0.0",
        versionCode: "100",
        locale: "",
        fallbackLocale: ""

      },
      auto: false,
      vueOptions: [{label: 2, value: 2}, {label: 3, value: 3}],
      localeOptions: [
        {label: '跟随系统或宿主的语言配置(auto)', value: 'auto'},
        {label: '英文(en)', value: 'en'},
        {label: '中文简体(zh-Hans)', value: 'zh-Hans'},
        {label: '中文繁体(zh-Hant)', value: 'zh-Hant'},
        {label: '法语(fr)', value: 'fr'},
        {label: '西班牙语(es)', value: 'es'}
      ],
      fallbackLocaleOptions: [
        {label: '英文(en)', value: 'en'},
        {label: '中文简体(zh-Hans)', value: 'zh-Hans'},
        {label: '中文繁体(zh-Hant)', value: 'zh-Hant'},
        {label: '法语(fr)', value: 'fr'},
        {label: '西班牙语(es)', value: 'es'}
      ]
    }
  },
  mounted() {
    document.body.addEventListener('click', function () {
      // 兼容处理
      var target = event.target || event.srcElement;
      // 判断是否匹配目标元素
      if (target.nodeName.toLocaleLowerCase() === 'a') {
        console.log('当前点击的 a 标签: ', target);

        // 对捕获到的 a 标签进行处理，需要先禁止它的跳转行为
        if (event.preventDefault) {
          event.preventDefault();
        } else {
          window.event.returnValue = true;
        }

        // 处理完 a 标签的内容，重新触发跳转，根据原来 a 标签页 target 来判断是否需要新窗口打开

        var url = target.getAttribute("href")
        window.java({
          request: url,
          persistent: false,
          onSuccess: function (response) {
            alert("返回的数据:" + response);
          }
        })
      }
    });
  },
  methods: {}
}
</script>

<style scoped>
</style>
