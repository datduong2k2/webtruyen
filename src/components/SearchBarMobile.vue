<template>
  <div class="search-bar-mobile">
    <input type="text" placeholder="Search..." />
  </div>
</template>

<script>
export default {
  name: "SearchBarMobile",
};
</script>

<style scoped>
/* CSS for search-bar-mobile styles */
.search-bar-mobile {
  display: block;
  text-align: center;
  align-items: center;
  height: 60px;
}

.search-bar-mobile input {
  height: 25px;
  padding: 10px;
  font-size: 18px;
  border-radius: 10px;
  border: 1px solid #ccc;
  background-color: rgb(255, 255, 255);
}
@media (min-width: 678px) {
  .search-bar-mobile {
    display: none;
  }
}
</style>
