<script setup></script>

<template>
  <div class="home-search">
    <input type="text" class="search-input" placeholder="Quick search: Destination or Activity" />
    <div class="search-button" role="button">
      <img src="./images/search.svg" alt="" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.home-search {
  width: 700px;
  height: 60px;
  margin: 0 auto;
  padding: 0 22px;
  border-radius: 50px;
  background-color: rgba(#d9d9d9, 0.5);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.search-input {
  font-size: 18px;
  font-weight: 700;
  line-height: 40px;
  color: #000;
  border: none;
  outline: none;
  background-color: transparent;
  width: calc(100% - 40px);

  &::placeholder {
    color: #5c5959;
  }
}

.search-button {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding-left: 10px;
  cursor: pointer;

  & > img {
    width: 30px;
    height: auto;
    object-fit: contain;
  }
}
</style>
