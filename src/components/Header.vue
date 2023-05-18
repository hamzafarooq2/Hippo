<template>
  <div class="navbar">
    <div class="logo">
      <span>Test Hippo <i class="fa-solid fa-hippo"></i></span>
    </div>
    <form action="#">
      <input type="search" class="search-data" placeholder="Search" />
      <button type="submit" class="fas fa-search"></button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.navbar {
  position: fixed;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #171c24;
  padding: 12px 12px 12px 12px;
  color: #fff;
}
.logo {
  font-size: 24px;
  font-weight: bold;
}
.navbar form {
  margin-right: 20px;
  display: flex;
  height: 34px;
  background: #171c24;
  border-radius: 4px;
  border: 1px solid rgba(155, 155, 155, 0.2);
}
.navbar form .search-data {
  height: 100%;
  width: 180px;
  padding: 0 10px;
  color: #fff;
  font-weight: 500;
  background: none;
  border: none;
  font-size: 17px;
  outline: none;
}
.fa-hippo {
  color: orangered;
}
.navbar form button {
  background: #ff3d00;
  border: none;
  cursor: pointer;
  font-size: 17px;
  color: #fff;
  border-radius: 2px;
  padding: 0 12px;
}
.navbar form button:hover {
  background: #e63600;
}
@media only screen and (max-width: 500px) {
  .navbar form {
    display: none;
  }
}
</style>
