<template>
  <div :class="['sidebar', { expanded: isExpanded }]">
    <div class="imgText">
      <i
        v-if="isExpanded"
        @click="toggleSidebar"
        class="fa-solid fa-xmark toggle"
      ></i>
      <i
        v-if="!isExpanded"
        @click="toggleSidebar"
        class="fa-solid fa-bars toggle"
      ></i>
    </div>
    <div class="imgText search-icon">
      <i
        v-if="!isExpanded"
        @click="toggleSidebar"
        class="fa-solid fa-magnifying-glass onhover"
      ></i>
      <div v-if="isExpanded">
        <form action="#">
          <input type="search" class="search-data" placeholder="Search" />
          <button type="submit" class="fas fa-search"></button>
        </form>
      </div>
    </div>
    <div class="imgText onhover">
      <i class="fa-brands fa-whatsapp"></i>
      <span v-if="isExpanded">Whatsapp</span>
    </div>
    <div class="imgText onhover">
      <i class="fa-brands fa-twitter"></i>
      <span v-if="isExpanded">Twitter</span>
    </div>
    <div class="imgText onhover">
      <i class="fa-brands fa-instagram"></i>
      <span v-if="isExpanded">Instagram</span>
    </div>
    <div class="imgText onhover">
      <i class="fa-brands fa-github"></i>
      <span v-if="isExpanded">Github</span>
    </div>
  </div>
</template>
<script>
export default {
  name: "Sidebar",
  data() {
    return {
      isExpanded: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isExpanded = !this.isExpanded;
    },
  },
};
</script>
<style scoped>
.sidebar {
  position: fixed;
  border-top-right-radius: 20px;
  margin-top: 64px;
  border-top: 1px solid white;
  display: flex;
  height: 100vh;
  flex-direction: column;
  align-items: flex-start;
  background-color: #171c24;
  transition: all 0.5s ease;
  padding: 0 8px;
  color: white;
}
.onhover:hover {
  color: orangered;
  cursor: pointer;
}
.imgText {
  margin: 0 8px;
  display: flex;
  align-items: center;
}
.search-icon {
  display: none;
}
.expanded {
  width: 200px; /* Expanded width of the sidebar */
}

.fa-brands {
  font-size: 28px;
  margin: 16px 0 20px 0;
  cursor: pointer;
}
span {
  margin-left: 12px;
}
form {
  display: flex;
  height: 34px;
  background: #171c24;
  border-radius: 4px;
  border: 1px solid rgba(155, 155, 155, 0.2);
  margin: 0px;
}
form .search-data {
  height: 100%;
  width: 150px;
  padding: 0 10px;
  color: #fff;
  font-weight: 500;
  background: none;
  border: none;
  font-size: 17px;
  outline: none;
}
.toggle {
  font-size: 24px;
  cursor: pointer;
  color: orangered;
  margin: 20px 0 20px 0;
}
.fa-solid {
  font-size: 26px;
  margin: 16px 0 20px 0;
}
form button {
  background: #ff3d00;
  border: none;
  cursor: pointer;
  font-size: 17px;
  color: #fff;
  border-radius: 2px;
  padding: 0 12px;
}
form button:hover {
  background: #e63600;
}
@media only screen and (max-width: 500px) {
  .search-icon {
    display: flex;
  }
}
</style>
