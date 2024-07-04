<!-- GET DATA FROM JSON-->
<!--
<template>
  <div class="new-books-block">

    <div class="header">
      <h2>TRUYỆN MỚI CẬP NHẬT</h2>
      <p class="text">XEM THÊM &gt;</p>
    </div>
    <hr class="horizontal-line" />
    <div class="options">
      <div
        v-for="(option, index) in options"
        :key="index"
        :class="{ selected: selectedOption === option }"
        @click="selectOption(option)"
      >
        {{ option }}
      </div>
    </div>

    <div class="books">
      <div v-if="selectedOption === 'Convert'" class="book-container">
        <div
          v-for="(book, index) in filteredBooks('convert')"
          :key="index"
          class="book"
        >
          <img :src="book.cover" alt="Book Cover" />
          <p>{{ book.title }}</p>
        </div>
      </div>
      <div v-if="selectedOption === 'Dịch'" class="book-container">
        <div
          v-for="(book, index) in filteredBooks('translate')"
          :key="index"
          class="book"
        >
          <img :src="book.cover" alt="Book Cover" />
          <p>{{ book.title }}</p>
        </div>
      </div>
      <div v-if="selectedOption === 'Ngôn tình'" class="book-container">
        <div
          v-for="(book, index) in filteredBooks('ngontinh')"
          :key="index"
          class="book"
        >
          <img :src="book.cover" alt="Book Cover" />
          <p>{{ book.title }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios"; // Import axios for making HTTP requests

export default {
  name: "NewBooksBlock",
  data() {
    return {
      selectedOption: "", // Lựa chọn hiện tại của người dùng
      options: ["Convert", "Dịch", "Ngôn tình"], // Các lựa chọn
      cardsData: [], // Dữ liệu sách từ file JSON
    };
  },
  methods: {
    // Hàm lấy dữ liệu từ file JSON
    async fetchData() {
      try {
        const response = await axios.get("/z_data/cardlist01.json"); // Thay đổi đường dẫn tới file JSON
        this.cardsData = response.data.cards;
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    },
    // Lọc và trả về danh sách sách theo type_transl và id lớn nhất
    filteredBooks(type) {
      // Lọc sách theo type_transl và sắp xếp theo id giảm dần, lấy 4 cuốn đầu tiên
      return this.cardsData
        .filter((book) => book.type_transl === type)
        .sort((a, b) => b.id - a.id)
        .slice(0, 4); // Lấy 4 cuốn sách đầu tiên
    },
    // Xử lý sự kiện khi người dùng chọn một lựa chọn
    selectOption(option) {
      this.selectedOption = option;
    },
  },
  mounted() {
    // Khi component được mount, gọi fetchData để tải dữ liệu từ JSON
    this.fetchData();
  },
};
</script>
-->

<template>
  <div class="new-books-block">
    <!-- Header -->
    <div class="header">
      <h2>TRUYỆN MỚI CẬP NHẬT</h2>
      <p class="text">XEM THÊM &gt;</p>
    </div>
    <hr class="horizontal-line" />
    <!-- Options -->
    <div class="options">
      <div
        v-for="(option, index) in options"
        :key="index"
        :class="{ selected: selectedOption === option }"
        @click="selectOption(option)"
      >
        {{ option }}
      </div>
    </div>

    <!-- Books -->
    <div class="books">
      <div v-if="selectedOption === 'Convert'" class="book-container">
        <div v-for="(book, index) in convertBooks" :key="index" class="book">
          <img :src="book.image" alt="Book Cover" />
          <p>{{ book.name }}</p>
        </div>
      </div>
      <div v-else>
        <p>Đang cập nhật danh sách cho lựa chọn '{{ selectedOption }}'</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewBooksBlock",
  data() {
    return {
      selectedOption: "Convert",
      options: ["Convert", "Dịch", "Ngôn tình"],
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
  font-weight: bold;
  font-size: 18px;
  background-color: #ffffff;
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
  width: 100%;
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
}

.book-container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}

.book {
  width: calc(25% - 5px);
  /* Để lại khoảng cách 5px giữa các ô */
  margin-bottom: 10px;
  text-align: center;
  color: black;
  cursor: none;
  text-decoration: none;
  margin-left: 5px;
}

.book img {
  width: 100%;
  aspect-ratio: 0.8;
  border-radius: 5px;
  object-fit: cover;
}

.book p {
  margin-top: 10px;
  font-weight: bold;
}

.horizontal-line {
  border: none;
  border-top: 1px solid #ccc;
  margin-top: 0;
}
</style>
