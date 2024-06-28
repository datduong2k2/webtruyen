<template>
  <div class="new-books-block">
    <!-- Header -->
    <div class="header">
      <h2>TRUYỆN XEM NHIỀU</h2>
      <p class="text">XEM THÊM &gt;</p>
    </div>
    <hr class="horizontal-line" />
    <!-- Options -->

    <!-- Books -->
    <div class="books">
      <div class="book-container">
        <div v-for="(book, index) in convertBooks" :key="index" class="book">
          <img :src="book.image" alt="Book Cover" />
          <p>{{ book.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewBooksBlock",
  data() {
    return {
      convertBooks: [
        {
          image:
            "https://www.nae.vn/ttv/ttv/public/images/story/0ab9fbe917d20cac55123ea2a3267ed3c3d8ad4921f25612adcd782c1826ca73.jpg",
          name: "Truyện 1",
        },
        {
          image:
            "https://www.nae.vn/ttv/ttv/public/images/story/8b07c672dd146c782feca74cb80c210657a9354f72833f3021ee8b08598d0f5e.jpg",
          name: "Truyện 2",
        },
        {
          image:
            "https://www.nae.vn/ttv/ttv/public/images/story/82d6ce1bf3b8a1947e62d15d3c9a7c7eeee13edbdbd54cc7cdc3191685518b59.jpg",
          name: "Truyện 3",
        },
        {
          image:
            "https://www.nae.vn/ttv/ttv/public/images/story/17b5efa8081ec08b62dc6372b6a130756409fa1b99e5908225c7b4a7902284de.jpg",
          name: "Truyện 4",
        },
      ],
    };
  },
  methods: {
    selectOption(option) {
      this.selectedOption = option;
    },
  },
};
</script>

<style scoped>
.new-books-block {
  background-color: #f2f2f2;
  padding: 20px;
  margin-bottom: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
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

.options {
  display: flex;
  justify-content: center;
  margin-bottom: 10px;
}

.options div {
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
}

.options div.selected {
  background-color: red;
  color: white;
}

.books {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.book-container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.book {
  width: calc(
    25% - 20px
  ); /* 25% để mỗi ô chiếm 25% chiều rộng của khối cha, trừ đi margin */
  margin-bottom: 20px; /* Khoảng cách dưới mỗi ô */
  background-color: white;
  padding: 10px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.book img {
  width: 100%; /* Hình ảnh chiếm toàn bộ chiều rộng của ô */
  border-radius: 8px;
}

.book p {
  margin-top: 10px;
  font-weight: bold;
}
.horizontal-line {
  border: none;
  border-top: 1px solid #ccc;
}
</style>
