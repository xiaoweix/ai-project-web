<template>
  <div class="main">
    <el-container>
      <el-aside width="200px" style="padding-top: 50px; height: 100vh">
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-sunny"></i>导航一</template>
            <el-menu-item-group>
              <el-menu-item index="1-1" @click="picToWord"><i class="el-icon-ice-cream-round"></i>文字识别</el-menu-item>
              <el-menu-item index="1-2" @click="imgToWord"><i class="el-icon-lollipop"></i>图像识别</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </div>
</template>

<script>
export default {
  name: "AiApprove",
  data() {
    return {
      title: '图象识别'
    }
  },
  methods: {
    picToWord() {
      this.$router.push('/picture')
    },
    imgToWord() {
      this.$router.push('/image')
    }
  }
}
</script>

<style scoped>
</style>