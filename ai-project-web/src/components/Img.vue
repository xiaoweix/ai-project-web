<template>
  <div class="container">
    <el-row :gutter="20">
      <el-col :span="24">
        <p class="headerTitle"><i class="el-icon-lollipop"></i><span>图像识别</span></p>
      </el-col>
      <el-col :span="12">
        <div
            style="width: 50%; border: 1px solid blue; margin: 30px 0;height: 700px;padding: 10px;box-sizing: border-box">
          <el-upload

              action="http://127.0.0.1:8081/imgRecognition"
              :on-remove="handleRemove"
              :file-list="fileList"
              list-type="picture"
              :on-success="handleAvatarSuccess"
          >
            <el-button size="small" type="primary">点击上传</el-button>
          </el-upload>
          <span
              style="font-size: 1px; color: red;position: absolute; top: 155px; left: 111px">只能上传jpg/png文件，且不超过500kb</span>
        </div>
      </el-col>
      <el-col :span="12">
        <div class="tHerder">
          <!--          <el-empty description="空空如也" style="padding-top: 200px" v-if="isShow"></el-empty>-->
          <div v-for="item in textList" class="textContainer">
            <p class="text-p">&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp{{ item }}</p>
          </div>
        </div>
      </el-col>

    </el-row>
  </div>

</template>

<script>

export default {
  name: "Img",
  computed: {},
  data() {
    return {
      isShow: true,
      fileList: [],
      textList: [],
    }
  },
  methods: {
    handleRemove() {
      console.log(this.fileList)
    },
    handleAvatarSuccess(res, file) {
      console.log(file)
      this.textList.push(res)
    },
  }
}
</script>

<style scoped>
.headerTitle {
  height: 100px;
  text-align: center;
  font-size: 25px;
  border: 1px red solid;
  line-height: 100px;
}

.headerTitle i {
  padding-right: 20px;
}

.textContainer {
  width: 95%;
  border: 1px solid yellow;
  margin: 10px auto;
}

.text-p {
  padding: 10px;
}

.tHerder {
  width: 100%;
  border: 1px solid blue;
  margin: 30px 0;
  height: 700px;
  overflow-x: hidden;
  overflow-y: scroll;
}
</style>