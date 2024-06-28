<template>
  <div class="login-page">
    <h2>Đăng nhập</h2>
    <form @submit.prevent="login">
      <div class="form-group">
        <label for="username">Tên đăng nhập:</label>
        <input type="text" id="username" v-model="username" required />
      </div>
      <div class="form-group">
        <label for="password">Mật khẩu:</label>
        <input type="password" id="password" v-model="password" required />
      </div>
      <div class="form-actions">
        <button type="submit">Đăng nhập</button>
        <a href="#" class="forgot-password">Quên mật khẩu?</a>
      </div>
    </form>
    <div class="social-login">
      <button @click="loginWithGoogle">Đăng nhập với Google</button>
      <button @click="loginWithFacebook">Đăng nhập với Facebook</button>
    </div>
    <div class="register-link">
      <p>Bạn chưa có tài khoản? <a href="#">Đăng ký ngay</a></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginPage",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      // Xử lý logic đăng nhập ở đây (chưa được triển khai)
      console.log("Đăng nhập với:", this.username, this.password);
    },
    loginWithGoogle() {
      // Xử lý đăng nhập với Google
      console.log("Đăng nhập với Google");
    },
    loginWithFacebook() {
      // Xử lý đăng nhập với Facebook
      console.log("Đăng nhập với Facebook");
    },
  },
};
</script>

<style scoped>
.login-page {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
}

h2 {
  text-align: center;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.form-actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 15px;
}

.form-actions button {
  padding: 10px 20px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

.forgot-password {
  font-size: 14px;
  text-decoration: none;
  color: #333;
}

.social-login {
  margin-top: 20px;
  text-align: center;
}

.social-login button {
  margin: 0 10px;
  padding: 10px 20px;
  background-color: #3b5998; /* Màu Facebook */
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

.social-login button:first-child {
  background-color: #db4437; /* Màu Google */
}

.register-link {
  margin-top: 20px;
  text-align: center;
}

.register-link a {
  text-decoration: none;
  color: #333;
  font-weight: bold;
}
</style>
