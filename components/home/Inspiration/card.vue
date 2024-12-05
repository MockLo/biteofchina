<script setup>
const props = defineProps({
  image: { type: String, default: '' },
  title: { type: String, default: '' },
  description: { type: String, default: '' },
});
</script>

<template>
  <section class="card">
    <img :src="image" />
    <p class="title">{{ title }}</p>
    <p class="desc">{{ description }}</p>
  </section>
</template>

<style lang="scss" scoped>
.card {
  width: 292px;
  cursor: pointer;

  & > img {
    width: 100%;
    height: 259px;
    object-fit: cover;
    border-radius: 12px;
    transition: all 200ms ease-in-out;
  }

  &:hover {
    & > img {
      transform: scale(1.03);
    }
  }
}

.title {
  margin-top: 16px;
  font-size: 20px;
  color: #222;
  font-weight: 700;
  line-height: 19px;
}

.desc {
  margin-top: 12px;
  color: #222;
  font-size: 15px;
  font-weight: 500;
  line-height: 19px;
}
</style>
