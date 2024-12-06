<script setup></script>

<template>
  <main class="home-page">
    <div class="page-top">
      <HomeNavBar />
      <HomeCarousel />
    </div>

    <div class="page-search">
      <HomeSearch />
    </div>

    <div class="page-content">
      <HomeFeaturedPackage />
      <HomeTopDestinations />
      <HomeInspiration />
    </div>
  </main>
</template>

<style lang="scss" scoped>
.page-top {
  position: relative;
  max-width: 2110px;
  margin: 0 auto;
}

.page-search {
  padding: 57px 0 46px;
}

.page-content {
  max-width: 1440px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 60px;
  padding: 0 80px 400px;
}
</style>
