<template>
  <div class="right-aside">
    <div class="header">
      <h2>TRUYỆN ĐÃ HOÀN THÀNH</h2>
      <p class="text">XEM THÊM &gt;</p>
    </div>
    <hr class="horizontal-line" />

    <!-- Repeat this block for each mobile-box item -->
    <div v-for="item in items" :key="item.id" class="mobile-box">
      <img :src="item.cover" :alt="item.title" />
      <div class="box-description">
        <p>
          <strong>{{ item.title }}</strong> <br />
          <span v-if="item.desc_short">{{ item.desc_short }}</span> <br />
          <span>Tác giả: {{ item.author }}</span> <br />
          <span>Chương hiện tại: {{ item.chapter }}</span> /
          <span>Tổng số chương: {{ item.chapter_all }}</span>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import cardlist01 from "@/z_data/cardlist01.json"; // Adjust the path based on your project structure

export default {
  data() {
    return {
      items: cardlist01.cards.slice(0, 5), // Lấy 5 cuốn sách đầu tiên từ JSON
    };
  },
};
</script>

<style scoped>
/* Add your scoped styles here */
.right-aside {
  grid-area: right-aside;
  background-color: #ffffff;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ffffff;
}

.header h2 {
  margin: 0;
  font-size: 14px;
}
.text {
  color: #007bff;
  cursor: pointer;
  font-size: 14px;
}
.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ffffff;
}

.section-header h5 {
  height: 20px;
}

.section-header a {
  color: #333;
  text-decoration: none;
}

.horizontal-line2 {
  width: 100%;
  height: 1px;
  background-color: #000;
  margin-bottom: 10px;
}

.mobile-box {
  height: 120px;
  display: flex;
  align-items: center;
  padding: 10px;
  background-color: #ffffff;
  border-bottom: 1px solid #ccc;
}

.mobile-box img {
  width: 80px;
  height: 100px;
  object-fit: cover;
  border-radius: 5px;
  margin-right: 10px;
}

.box-description {
  flex: 1;
  font-size: 14px;
  font-family: "Times New Roman", Times, serif;
  text-align: left;
}
.horizontal-line {
  border: none;
  border-top: 1px solid #ccc;
  margin-top: 0;
}
/* Add more styles as needed */
</style>
