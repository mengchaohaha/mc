<template>
    <div class="login-wr">
        <el-form label-position="top" label-width="80px" class="login-form">
            <h2>用户登录</h2>
            <el-form-item label="用户名">
                <el-input ></el-input>
            </el-form-item>
            <el-form-item label="密码">
                <el-input  type="password"></el-input>
            </el-form-item>
            <el-form-item>    
                <el-button class="btn" type="primary">登录</el-button>
           </el-form-item>
        </el-form>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
.login-wr {
    height: 100%;
    background-color: #324152;
    display: flex;
    justify-content: center;
    align-items: center;

}
.login-form {
    width: 500px;
    padding:30px;
    border-radius: 5px;
    background-color: #fff;
}
.btn {
    width: 100%;
}
</style>


