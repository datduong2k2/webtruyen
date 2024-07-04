<template>
  <div class="slideshow">
    <div
      class="slide"
      v-for="(image, index) in images"
      :key="index"
      :class="{ active: index === currentIndex }"
    >
      <img :src="image.src" :alt="'Slideshow Image ' + (index + 1)" />
    </div>

    <!-- Thanh điều hướng (pagination) -->
    <div class="pagination">
      <span
        class="dot"
        v-for="(image, index) in images"
        :key="index"
        :class="{ active: index === currentIndex }"
        @click="goToSlide(index)"
      ></span>
    </div>

    <!-- Biểu tượng chuyển slide -->
    <div class="controls">
      <span class="prev" @click="prevSlide">&#10094;</span>
      <span class="next" @click="nextSlide">&#10095;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "SlideShow",
  data() {
    return {
      currentIndex: 0,
      intervalId: null,
      images: [
        { src: "https://truyen.tangthuvien.vn/images/slide8.jpg" },
        { src: "https://truyen.tangthuvien.vn/images/slide7.jpg" },
        { src: "https://truyen.tangthuvien.vn/images/slide9.jpg" },
      ],
    };
  },
  mounted() {
    this.startSlideshow();
  },
  methods: {
    startSlideshow() {
      this.intervalId = setInterval(() => {
        this.nextSlide();
      }, 3000); // Thay đổi slide mỗi 3 giây (3000 milliseconds)
    },
    stopSlideshow() {
      clearInterval(this.intervalId);
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevSlide() {
      this.currentIndex =
        this.currentIndex === 0
          ? this.images.length - 1
          : this.currentIndex - 1;
    },
    goToSlide(index) {
      this.currentIndex = index;
    },
  },
  beforeUnmount() {
    this.stopSlideshow();
  },
};
</script>

<style scoped>
.slideshow {
  margin-top: 10px;
  overflow: hidden;
  position: relative;
  margin-bottom: 10px;
}

.slideshow .slide {
  display: none;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.slideshow .slide.active {
  display: block;
}

.slideshow .slide img {
  width: 100%;
  height: 100%;
}

/* CSS cho thanh điều hướng (pagination) */
.pagination {
  text-align: center;
  margin-top: 10px;
}

.pagination .dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: #bbb;
  border-radius: 50%;
  margin: 0 5px;
  cursor: pointer;
}

.pagination .dot.active {
  background-color: #555;
}

/* CSS cho biểu tượng chuyển slide */
.controls {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 100%;
  display: flex;
  justify-content: space-between;
  font-size: 24px;
  color: #fff;
  cursor: pointer;
  z-index: 1;
  margin-bottom: 10px;
}

.controls .prev,
.controls .next {
  user-select: none;
}

.controls .prev {
  left: 20px;
}

.controls .next {
  right: 20px;
}
</style>
