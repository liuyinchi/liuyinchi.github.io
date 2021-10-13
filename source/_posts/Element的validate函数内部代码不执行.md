---
title: Element的validate函数内部代码不执行
categories: 问题
date: 2021-4-16
tags: 已解决
---
  
  ### 错误案例： button按钮无法提交
  
  ``` bash
  html
  
  <el-dialog
    title="提示"
    :visible.sync="addVisible"
    width="50%"
    @close="addDialogClose">
    <el-form ref="addFormRef" :model="addForm" :rules="addFormRules"  label-width="80px">
      <el-form-item label="用户名" prop="username">
        <el-input v-model="addForm.username"></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input v-model="addForm.password"></el-input>
      </el-form-item>
      <el-form-item label="邮箱" prop="email">
        <el-input v-model="addForm.email"></el-input>
      </el-form-item>
      <el-form-item label="手机" prop="mobile">
        <el-input v-model="addForm.mobile"></el-input>
      </el-form-item>
    </el-form>
    <span slot="footer" class="dialog-footer">
      <el-button @click="addVisible = false">取 消</el-button>
      <el-button type="primary" @click="addUser">确 定</el-button>
    </span>
  </el-dialog>
  
  js
  
  var checkEmail = (rules, value, callback) => {
    if(!value){
      return callback(new Error('邮箱不能为空'));
    }
    const regEmail = /^[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$/
    if(regEmail.test(value) == false){
      return callback(new Error('邮箱格式有误'));
    }
  }
  ```
  
  ### 解决办法
  segmentfault网站
  xzzfxz用户
  经过我的细心检查不是validate的问题，而是你的问题。
  this.$refs[ref].validate()是一个promise函数，我把它输出了一下，发现它一直是pending状态，证明它一直在执行（因为这是一个异步的，所以能输出4），也就是说你的rule有问题。
  事实证明你写的检查手机号的自定义规则有问题：你少写了一个callback()，以下是我改好的
  
  ``` bash
  js
  
  var checkEmail = (rules, value, callback) => {
    if(!value){
      return callback(new Error('邮箱不能为空'));
    }
    const regEmail = /^[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+$/
    if(regEmail.test(value) == false){
      return callback(new Error('邮箱格式有误'));
    }
	callback() //这里没有写callback
  }
  ```