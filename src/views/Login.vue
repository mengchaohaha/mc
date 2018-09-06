<template>
    <div class="login-wr">
        <el-form label-position="top" label-width="80px" class="login-form" :model="dormData">
            <h2>用户登录</h2>
            <el-form-item label="用户名">
                <el-input v-model="formData.username"></el-input>
            </el-form-item>
            <el-form-item label="密码">
                <el-input  type="password" v-model="formData.password"></el-input>
            </el-form-item>
            <el-form-item>    
                <el-button @click="handleLogin" class="btn" type="primary">登录</el-button>
           </el-form-item>
        </el-form>
    </div>
</template>

<script>
export default {
    data () {
        return {
            formData:{
                username:'',
                password:''
            }
        }
    },
    methods: {
        handleLogin() {
            this.$http
            .post('login',this.formData)
            .then((response) => {
                // response.data.meta.status
                const { meta: {msg,status}} = response.data;
                if(status === 200) {
                    this.$message.success(msg);
                    // 记录token
                    sessionStorage.setItem('token',response.data.data.token)
                }else {
                    this.$message.error(msg);
                }
            })
            .catch((err) => {
                console.log(err);
            });
        }
    }
};
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


