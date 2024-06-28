<template>
  <div class="home-page">
    <!-- Navbar -->
    <!-- Search bar -->
    <div class="search-bar">
      <input type="text" placeholder="Tìm kiếm tác giả hoặc truyện" />
    </div>
    <nav class="navbar">
      <ul>
        <li>
          <img src="../assets/logo.png" width="40" height="40" />
          <a href="#">Thể loại</a>
        </li>
        <li>
          <img src="../assets/logo.png" width="40" height="40" /><a href="#"
            >Xếp hạng</a
          >
        </li>
        <li>
          <img src="../assets/logo.png" width="40" height="40" /><a href="#"
            >Bộ lọc</a
          >
        </li>
        <li>
          <img src="../assets/logo.png" width="40" height="40" /><a href="#"
            >Top user</a
          >
        </li>
        <li>
          <img src="../assets/logo.png" width="40" height="40" /><a href="#"
            >Review</a
          >
        </li>
      </ul>
    </nav>

    <!-- Slideshow -->
  </div>
</template>

<script>
export default {
  name: "NavbaPage",
};
</script>

<style scoped>
.home-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.navbar {
  margin-top: 10px;
  width: 100%;
  background-color: #ffffff;
  color: #fff;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 10px 0;
}

.navbar ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.navbar ul li {
  margin: 0 10px;
}

.navbar ul li a {
  color: #000000;
  text-decoration: none;
  font-size: 12px;
}

.search-bar {
  display: flex;
  align-items: center;
}

.search-bar input[type="text"] {
  padding: 10px;
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  align-items: center;
}

.search-bar button {
  padding: 10px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

.search-bar button:hover {
  background-color: #45a049;
}
</style>
