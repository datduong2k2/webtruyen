<template>
  <header class="site-header">
    <div class="logo">
      <img src="../assets/logo.png" alt="Logo" />
      <p>{{ nameWeb }}</p>
    </div>
    <!-- Sử dụng router-link để điều hướng đến trang Login -->
    <router-link to="./LoginPage.vue">
      <button>Login</button>
    </router-link>
  </header>
</template>
<script>
export default {
  name: "HeaderPage",
  data() {
    return {
      nameWeb: "Truyện",
    };
  },
};
</script>

<style scoped>
/* CSS cho header */
.site-header {
  background-color: #ffffff;
  color: #000000; /* Màu chữ là đen cho tương phản tốt hơn */
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap; /* Cho phép các phần tử chuyển dòng khi cần thiết */
}

.logo {
  display: flex;
  align-items: center;
}

.logo img {
  height: 40px; /* Điều chỉnh chiều cao của logo */
  margin-right: 10px; /* Khoảng cách giữa logo và văn bản */
}

/* Button "Tài khoản" */
.site-header button {
  background-color: rgb(40, 172, 28);
  color: rgb(255, 255, 255);
  padding: 5px;
  border-block-color: rgb(46, 38, 38);
  border-radius: 10px;
  font-size: 12px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

@media (max-width: 768px) {
  .site-header {
    flex-direction: row;
    text-align: center;
  }

  .logo {
    margin-bottom: 10px;
  }

  .search-form {
    margin-bottom: 10px;
    width: 20;
  }
}
</style>
