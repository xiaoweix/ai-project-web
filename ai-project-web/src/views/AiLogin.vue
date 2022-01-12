<template>
    <div class="page">
      <div class="login-container">
        <div class="left-container">
          <div class="title"><span>登录</span></div>
          <div class="input-container">
            <input type="text" name="username" placeholder="用户名" v-model="loginForm.userName">
            <input type="password" name="password" placeholder="密码" v-model="loginForm.passWord">
          </div>
          <div class="message-container">
            <span>忘记密码</span>
          </div>
        </div>
        <div class="right-container">
          <div class="regist-container">
            <span class="regist">注册</span>
          </div>
          <div class="action-container">
            <span @click="login">Login</span>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import {Loading} from "element-ui";

export default {
  name: "home",
  data() {
    return {
      loginForm: {
        userName: '',
        passWord: '',
      },
    }
  },
  methods: {
    login() {
      const options = {
        text: '拼命加载中...',
        background: 'rgba(0,0,0,.5)',
        spinner: 'el-icon-loading',
      }
      let loadingInstance = Loading.service(options);
      setTimeout(() => {
        loadingInstance.close();
        this.$router.push('/AiInterface')
      },2000)
    }
  }
}
</script>

<style scoped>
.page {
  height: 100%;
  background-image: linear-gradient(to bottom right, rgb(118, 76, 163), rgb(92, 103, 211));
}

.login-container {
  width: 600px;
  height: 315px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 15px;
  box-shadow: 0 10px 50px 0px rgb(59, 45, 159);
  background-color: rgb(95, 76, 194);
}

.left-container {
  display: inline-block;
  width: 330px;
  border-top-left-radius: 15px;
  border-bottom-left-radius: 15px;
  padding: 60px;
  background-image: linear-gradient(to bottom right, rgb(118, 76, 163), rgb(92, 103, 211));
}

.title {
  color: #fff;
  font-size: 18px;
  font-weight: 200;
}

.title span {
  border-bottom: 3px solid rgb(237, 221, 22);
}

.input-container {
  padding: 20px 0;
}

input {
  border: 0;
  background: none;
  outline: none;
  color: #fff;
  margin: 20px 0;
  display: block;
  width: 100%;
  padding: 5px 0;
  transition: .2s;
  border-bottom: 1px solid rgb(199, 191, 219);
}

input:hover {
  border-bottom-color: #fff;
}

::-webkit-input-placeholder {
  color: rgb(199, 191, 219);
}

.message-container {
  font-size: 14px;
  transition: .2s;
  color: rgb(199, 191, 219);
  cursor: pointer;
}

.message-container:hover {
  color: #fff;
}

.right-container {
  width: 145px;
  display: inline-block;
  height: calc(100% - 120px);
  vertical-align: top;
  padding: 60px 0;
}

.regist-container {
  text-align: center;
  color: #fff;
  font-size: 18px;
  font-weight: 200;
}

.regist-container span {
  border-bottom: 3px solid rgb(237, 221, 22);
}

.action-container {
  font-size: 10px;
  color: #fff;
  text-align: center;
  position: relative;
  top: 200px;
}

.action-container span {
  border: 1px solid rgb(237, 221, 22);
  padding: 10px;
  display: inline;
  line-height: 20px;
  border-radius: 20px;
  position: absolute;
  bottom: 10px;
  left: calc(72px - 20px);
  transition: .2s;
  cursor: pointer;
}

.action-container span:hover {
  background-color: rgb(237, 221, 22);
  color: rgb(95, 76, 194);
}
</style>