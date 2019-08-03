<template>

  <div class="login-wrap" :style="divimg">
  <h1>22222222222222</h1>
    <div>
      <p class="p-title">LCG我爱编码,蛟龙在线,欢迎点评</p>
    </div>
    <div class="ms-login">
      <div class="ms-title">
        欢迎使用
      </div>
      <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="0px" class="ms-content">
        <el-form-item prop="username">
          <el-input v-model="ruleForm.username" placeholder="请输入用户名">
            <el-button slot="prepend" icon="iconfont icon-guanliyuanrenzheng"></el-button>
          </el-input>
        </el-form-item>
        <el-form-item  prop="password">
          <el-input type="password" placeholder="请输入认证密码" v-model="ruleForm.password" @keyup.enter.native="submitForm('ruleForm')">
            <el-button slot="prepend" icon="iconfont icon-yuechi"></el-button>
          </el-input>
        </el-form-item>

        <el-form-item prop="code">
          <div class="form-inline-input">
            <div class="code-box" id="code-box">
              <input ref="coderef" type="text" name="code" class="code-input" />
              <p></p>
              <span style="color:#909399">
                     拖动验证
                  </span>
            </div>
          </div>
        </el-form-item>


        <div class="login-btn">
          <el-button type="primary" @click="submitForm('ruleForm')">登录</el-button>
        </div>
        <!-- 登录进度 -->
        <el-progress ref="jindu" :style="jindustyle"  :text-inside="true"
                     :stroke-width="18"
                     :percentage="percent"
                     status="success"></el-progress>

      </el-form>
    </div>

  </div>

</template>

<script>

    export default {
        name: 'App',
      data(){
        return{
          divimg:{//背景图片的使用
            backgroundImage:"url(" + require('../../assets/yun.jpg') + ")",
            backgroundRepeat: "no-repeat",
            height:"100%",
            width:"100%",
            overflow:"hidden",
            backgroundSize:"cover"
          },
          percent:0,
          jindustyle:{
            display:'none'
          },
          ruleForm: {
            username:'zhangsan',
            password:'123456'
          },
          rules: {
            username: [
              { required: true, message: '请输入用户名', trigger: 'blur' }
            ],
            password: [
              { required: true, message: '请输入密码', trigger: 'blur' }
            ]
          }
        }
      },

    }
</script>

<style scoped>
  /*  .login-wrap{
      position: relative;
      width:100%;
      height:100%;
      background-image: url(../../assets/login-bg.jpg);
      background-size: 100%;
    }*/
  .ms-title{
    width:100%;
    line-height: 50px;
    text-align: left;
    font-size:20px;
    color: #fff;
    font-style:italic;
    border-bottom: 1px solid #ddd;
  }
  .ms-login{
    position: absolute;
    left:70%;
    top:50%;
    width:350px;
    margin:-190px 0 0 -175px;
    border-radius: 5px;
    background: rgba(255,255,255, 0.3);
    overflow: hidden;
  }
  .ms-content{
    padding: 30px 30px;
  }
  .login-btn{
    text-align: center;
  }
  .login-btn button{
    width:100%;
    height:36px;
    margin-bottom: 10px;
  }
  .login-tips{
    font-size:12px;
    line-height:30px;
    color:#fff;
  }

  /** 滑动验证start **/
  .form-inline-input{
    border:1px solid #dadada;
    border-radius:5px;
  }
  .form-inline-input input,
  .code-box{
    padding: 0 3px;
    width: 290px;
    height: 40px;
    color: #fff;
    text-shadow: 0px 0px 0px black;
    background: #efefef;
    border: 0;
    border-radius: 5px;
    outline: none;
  }
  .code-box{
    position: relative;
  }
  .code-box p,
  .code-box span{
    display:block;
    position: absolute;
    left: 0;
    height: 40px;
    text-align: center;
    line-height: 40px;
    border-radius: 5px;
    padding:0;
    margin:0;
  }
  .code-box span{
    width: 40px;
    background-color:#fff;
    font-size: 16px;
    cursor: pointer;
    margin-right:1px;
  }
  .code-box p{
    width: 0;
    background-color: #FFFF99;
    overflow: hidden;
    text-indent: -20px;
    transition: background 1s ease-in;
  }
  .code-box .code-input{
    display: none;
  }
  .code-box .code-input{
    display: none;
  }
  .form-inline-input{
    border:1px solid #dadada;
    border-radius:5px;
  }
  .form-inline-input input,
  .code-box{
    padding: 0 3px;
    width: 285px;
    height: 40px;
    color: #fff;
    text-shadow: 0px 0px 0px black;
    background: #efefef;
    border: 0;
    border-radius: 5px;
    outline: none;
  }
  .code-box{
    position: relative;
  }
  .code-box p,
  .code-box span{
    display:block;
    position: absolute;
    left: 0;
    height: 40px;
    text-align: center;
    line-height: 40px;
    border-radius: 5px;
    padding:0;
    margin:0;
  }
  .code-box span{
    width: 70px;
    background-color:#fff;
    font-size: 12px;
    cursor: pointer;
    margin-right:1px;
  }
  .code-box p{
    width: 0;
    background-color: #F5F7FA;
    overflow: hidden;
    text-indent: -20px;
    transition: background 1s ease-in;
  }
  .code-box .code-input{
    display: none;
  }
  .code-box .code-input{
    display: none;
  }
  .p-title{
    color: white;
    font-size: 16px;
    text-align: left;
    padding-left: 20px;
    font-style:italic
  }
  /** 滑动验证end **/
</style>
