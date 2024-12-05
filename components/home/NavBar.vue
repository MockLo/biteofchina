<script setup></script>

<template>
  <nav class="home-nav-bar">
    <img class="nav-logo" src="./images//boc-logo.jpg" />
    <div class="sub-menus">
      <div class="sub-menu">Activity</div>
      <div class="sub-menu">Inspiration</div>
      <div class="sub-menu">Assistant</div>
      <div class="sub-menu">Contact us</div>
      <div class="person">
        <img src="./images/line-md_person.svg" />
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
.home-nav-bar {
  position: absolute;
  width: 100%;
  height: 60px;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.25);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 32px;
  z-index: 2;
}

.nav-logo {
  width: auto;
  height: 100%;
}

.sub-menus {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 56px;
}

.sub-menu {
  color: #d9d9d9;
  font-size: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all ease 200ms;

  /* &:hover {
    color: #06f;
  } */
}

.person {
  cursor: pointer;

  /* &:hover {
    color: #06f;
  } */
}
</style>
