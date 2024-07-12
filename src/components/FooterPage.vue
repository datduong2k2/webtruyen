<template>
  <footer class="footerPage">
    <hr class="horizontal-line" />
    <p>
      <span>© 2007 Tàng Thư Viện - Chính sách</span><br />
      Tàng Thư Viện là sân chơi mở và free cho cộng đồng fan kiếm hiệp, tiên
      hiệp, ngôn tình. Chúc các bạn có những giây phút thư giãn thoải mái sau
      giờ làm việc và học tập căng thẳng.
    </p>
  </footer>
</template>

<script>
export default {
  name: "FooterPage",
};
</script>

<style scoped>
.footer {
  background-color: #333;
  color: #fff;
  text-align: center;
  padding: 20px;
  position: absolute;
  bottom: 0;
  width: 100%;
}
.footer p {
  margin: 0;
  font-size: 10px;
  line-height: 1.5;
}
.footer span {
  font-weight: bold;
}
.horizontal-line {
  border: none;
  border-top: 1px solid #ccc;
}
</style>
