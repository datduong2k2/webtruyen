<template>
  <div class="header">
    <div class="logo">
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTnRyNjTC0YyGo6zBrXw9m7FABlPEjhM14NiQ&s"
        alt="logo"
      />
    </div>
    <div class="search-bar">
      <input type="text" placeholder="Search..." />
    </div>
    <div class="account">Account</div>
    <div class="account2">
      <img
        src="https://banner2.cleanpng.com/20180516/zq/kisspng-computer-icons-google-account-icon-design-login-5afc02dab4a218.0950785215264652427399.jpg"
        alt="login"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderPage",
};
</script>

<style scoped>
/* CSS for header styles */
.header {
  margin-top: 20px;
  grid-area: header;
  background-color: #ffffff;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.logo {
  justify-content: flex-start;
}

.header .logo img {
  height: 60px;
  width: auto;
}

.search-bar {
  flex: 2;
  text-align: center;
}

.search-bar input {
  width: 100%;
  max-width: 300px;
  height: 25px;
  padding: 8px;
  font-size: 18px;
  border-radius: 10px;
  border: 1px solid #ccc;
}

.account {
  text-align: right;
  position: relative;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 10px;
}

.account::after {
  margin-left: 10px;
}

@media (min-width: 678px) {
  .account2 {
    display: none;
  }
}
@media (max-width: 678px) {
  .header .search-bar {
    display: none;
  }
  .account {
    display: none;
  }

  .account2 {
    display: flex;
    /* Display account as flex container */
    justify-content: flex-end;
    /* Push content to the right */
    align-items: center;
    /* Center align items vertically */
    flex: 1;
    /* Occupy remaining space */
  }
  .account2 img {
    display: flex;
    justify-content: flex-end;
    height: 20px;
    width: 20px;
  }
  .account2 img {
    display: flex;
    justify-content: flex-end;
    /* Push content to the right */
    height: 30px;
    width: 30px;
  }

  .header .logo img {
    height: 30px;
    width: auto;
  }
}
</style>
