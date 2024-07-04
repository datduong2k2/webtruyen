<template>
  <div class="right-aside">
    <div class="header">
      <h2>TRUYỆN ĐỀ XUẤT</h2>
      <p class="text">XEM THÊM &gt;</p>
    </div>
    <hr class="horizontal-line" />

    <!-- Repeat this block for each mobile-box item -->
    <div v-for="item in items" :key="item.id" class="mobile-box">
      <img :src="item.imageUrl" :alt="item.alt" />
      <div class="box-description">
        <p>
          {{ item.title }} <br />
          Thể loại: {{ item.genre }} <br />
          Tác giả: {{ item.author }} <br />
          Lượt xem: {{ item.views }} <br />
          Tình trạng: {{ item.status }} <br />
          Số chương: {{ item.chapters }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          id: 1,
          imageUrl:
            "https://www.nae.vn/ttv/ttv/public/images/story/0ab9fbe917d20cac55123ea2a3267ed3c3d8ad4921f25612adcd782c1826ca73.jpg",
          alt: "Image 1",
          title: "Luân hồi lạc viên",
          genre: "Đồng nhân",
          author: "Na nhất chích vân tử",
          views: "847948489",
          status: "chưa hoàn thành",
          chapters: "899",
        },
        {
          id: 2,
          imageUrl:
            "https://www.nae.vn/ttv/ttv/public/images/story/0ab9fbe917d20cac55123ea2a3267ed3c3d8ad4921f25612adcd782c1826ca73.jpg",
          alt: "Image 1",
          title: "Luân hồi lạc viên",
          genre: "Đồng nhân",
          author: "Na nhất chích vân tử",
          views: "847948489",
          status: "chưa hoàn thành",
          chapters: "899",
        },
        // Add more items as needed
      ],
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
  height: 100px;
  display: flex;
  align-items: center;
  padding: 10px;
  background-color: #ffffff;
}

.mobile-box img {
  width: 70px;
  aspect-ratio: 0.7;
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
