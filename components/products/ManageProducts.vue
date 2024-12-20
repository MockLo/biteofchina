<script setup>
import { NDataTable } from 'naive-ui';

const columns = [
  {
    title: 'id',
    key: 'id',
  },
  {
    title: 'title',
    key: 'title',
  },
  {
    title: 'location',
    key: 'location',
  },
  {
    title: 'category',
    key: 'category',
  },
  {
    title: 'create time',
    key: 'create_time',
  },
  {
    title: 'modify time',
    key: 'modify_time',
  },
];

const data = Array.from({ length: 46 }).map((_, index) => ({
  key: index,
  title: `Edward King ${index}`,
  category: 32,
  location: `London, Park Lane no. ${index}`,
}));
const pagination = { pageSize: 15 };
</script>

<template>
  <main class="page">
    <section class="section">
      <h1 class="title">Manage Your Travel Products</h1>

      <NDataTable class="my-table" size="large" :columns="columns" :data="data" :pagination="pagination" />
    </section>
  </main>
</template>

<style lang="scss" scoped>
.page {
  height: 100vh;
  overflow: hidden;
  background-color: #f3f4f6;
}

.section {
  width: 1200px;
  margin: 40px auto;
  padding: 36px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0px 4px 6px -4px rgba(0, 0, 0, 0.1), 0px 10px 15px -3px rgba(0, 0, 0, 0.1), 0px 0px 0px 0px #000,
    0px 0px 0px 0px #000;
}

.title {
  color: #1f2937;
  font-size: 24px;
  font-weight: 600;
}

.my-table {
  margin-top: 36px;
}
</style>
