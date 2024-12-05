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
    <div class="card-top">
      <p class="title">{{ title }}</p>
      <p class="desc">{{ description }}</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.card {
  width: 624px;
  height: 362px;
  overflow: hidden;
  position: relative;
  border-radius: 12px;
  cursor: pointer;

  & > img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: all 200ms ease;
  }

  &-top {
    position: absolute;
    left: 0;
    bottom: 0;
    padding: 0 22px 10px;
    transition: all 200ms ease-in-out;
    transform-origin: left bottom;
  }

  &:hover {
    & > img {
      transform: scale(1.04);
    }

    .card-top {
      transform: scale(1.04);
    }
  }
}

.title {
  font-size: 20px;
  color: #fff;
  font-weight: 700;
  line-height: 19px;
}

.desc {
  margin-top: 4px;
  color: #fff;
  font-size: 15px;
  font-weight: 500;
  line-height: 19px;
}
</style>
