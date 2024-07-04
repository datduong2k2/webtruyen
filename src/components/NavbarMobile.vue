<template>
  <div class="mobile-navbar">
    <a href="#">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMzigP1lbSxHKc43srls1iwvp_ZQQorHj9VA&s"
      />
      Thể loại
    </a>
    <a href="#">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMzigP1lbSxHKc43srls1iwvp_ZQQorHj9VA&s"
      />
      Xếp hạng
    </a>
    <a href="#">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMzigP1lbSxHKc43srls1iwvp_ZQQorHj9VA&s"
      />
      Bộ lọc
    </a>
    <a href="#">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMzigP1lbSxHKc43srls1iwvp_ZQQorHj9VA&s"
      />
      Top User
    </a>
    <a href="#">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMzigP1lbSxHKc43srls1iwvp_ZQQorHj9VA&s"
      />
      Review
    </a>
    <!-- Other mobile nav links -->
  </div>
</template>

<script>
export default {
  name: "MobileNavbar",
};
</script>

<style scoped>
/* CSS for mobile-navbar styles */
.mobile-navbar {
  flex-grow: 1;
  display: flex;
  justify-content: space-around;
  grid-area: mobile-navbar;
  background-color: #ffffff;
  height: auto;
  margin-bottom: 20px;
}

.mobile-navbar a {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #333;
  font-size: auto;
}

.mobile-navbar img {
  width: 70%;
  aspect-ratio: 1;
  margin-bottom: 5px;
}
</style>
