
<template>
  <div style="width: 100% ; display: flex">
      <el-input :model="url" style="flex: 1"></el-input>
      <el-button type="primary" style="float: right;margin-left: 5px" @click="click" >{{text}}
      </el-button>
      <input hidden="hidden" type="file"  ref="selectFiles" @change="fileChange">
  </div>
</template>

<style scoped>

</style>

<script >
export default {
    name: "FileSelect",
    props:{
        url:String,
        text:String
    },
    methods:{
        click(){
            this.$refs.selectFiles.dispatchEvent(new MouseEvent('click'));
        },
        fileChange(){
            console.log(this.$refs.selectFiles.files[0].path)
        }
    }
}
</script>