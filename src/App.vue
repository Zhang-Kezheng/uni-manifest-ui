<template>
  <Main/>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
      Main
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
          persistent:false,
          onSuccess: function(response) {
            alert("返回的数据:"+response);
          }
        })
      }
    });
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
a {
    color: #1d31ff;
    font-size: 10px;
}
.tab-Title{
    font-size: 30px;
}
.second-Title{
  font-size: 20px;
}
</style>
