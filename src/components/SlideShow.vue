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
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      }, 3000); // Thay đổi slide mỗi 3 giây (3000 milliseconds)
    },
    stopSlideshow() {
      clearInterval(this.intervalId);
    },
  },
  beforeUnmount() {
    this.stopSlideshow();
  },
};
</script>

<style scoped>
.slideshow {
  overflow: hidden;
  position: relative;
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
</style>
