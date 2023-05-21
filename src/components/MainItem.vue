<template>
  <div>
      <el-row>
          <span  class="title" v-html="title">
          </span>
      </el-row>
      <el-row>
          <span  class="description" v-html="description">
          </span>
      </el-row>
      <el-row>
          <slot name="body">
          </slot>
      </el-row>
  </div>
</template>

<style>
.title{
    font-size: 10px;
}
.description{
    font-size: 10px;
  color: rgba(61, 56, 56, 0.49);
}
</style>
<script >
export default {
    name: "MainItem",
    props:{
        title:String,
        description:String
    }
}
</script>