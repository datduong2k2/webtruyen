<template>
  <div>
    <header-page />
    <slide-show />
    <navba-page />
    <img
      src="https://truyen.tangthuvien.vn/images/banner-app-ttv.jpg"
      alt="tải app"
      class="full-width-image"
    />
    <new-update />
    <top-view />
    <footer-page />
  </div>
</template>

<script>
import HeaderPage from "./components/HeaderPage.vue";
import NavbaPage from "./components/NavbaPage.vue";
import SlideShow from "./components/SlideShow.vue";
import NewUpdate from "./components/NewUpdate.vue";
import FooterPage from "./components/FooterPage.vue";
import TopView from "./components/TopView.vue";
export default {
  name: "App",
  components: {
    HeaderPage,
    NavbaPage,
    SlideShow,
    NewUpdate,
    FooterPage,
    TopView,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #585c5f;
}
.full-width-image {
  width: 100%;
  height: auto; /* Đảm bảo tỷ lệ hình ảnh không bị bóp méo */
}
</style>
