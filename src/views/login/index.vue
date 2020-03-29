<template>
  <div class="box">
    <el-card class="login-card">
      <div class="logo">
        <img src="../../assets/img/logo_index.png"
             alt="">
      </div>
      <el-form style="margin-top:20px"
               :rules="rules"
               :model="ruleForm">
        <el-form-item>
          <el-input v-model="ruleForm.username"></el-input>
        </el-form-item>
        <el-form-item>
          <el-input v-model="ruleForm.password"
                    style="width:250px"></el-input>
          <el-button style="float:right">发送验证码</el-button>
        </el-form-item>
        <el-form-item style="margin-top:-20px">
          <el-checkbox>我已阅读并同意用户协议和隐私条款</el-checkbox>
        </el-form-item>
        <el-form-item style="margin-top:-10px">
          <el-button type="primary"
                     style="width:100%">登录</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ruleForm: {
        username: '',
        password: ''
      }
    }
  },
  rules: {
    username: [
      { required: true, message: '请输入用户名', trigger: 'blur' },
      { min: 11, max: 11, message: '长度为11个字符', trigger: 'blur' }
    ],
    password: [
      { required: true, message: '请输入密码', trigger: 'blur' },
      { min: 6, max: 16, message: '长度为6 到 16 个字符之间', trigger: 'blur' }
    ]
  }
}
</script>

<style lang="less" scoped>
.box {
  background-image: url("../../assets/img/login_bg.jpg");
  //当前可视屏幕的100%
  height: 100vh;
  background-size: cover;
  display: flex; //flex布局默认横向
  justify-content: center; //水平居中
  align-items: center; //垂直居中
  // position: relative;
  .login-card {
    width: 440px;
    height: 300px;
    // position: absolute;
    // top: 50%;
    // left: 50%;
    // transform: translate(-50%,-50%);
    .logo {
      text-align: center;
      img {
        height: 45px;
      }
    }
  }
}
</style>
