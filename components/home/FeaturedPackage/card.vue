<script setup>
const props = defineProps({
  image: { type: String, default: '' },
  title: { type: String, default: '' },
  position: { type: String, default: '' },
  duration: { type: String, default: '' },
  price: { type: String, default: '' },
  priceUnit: { type: String, default: '' },
  score: { type: String, default: '' },
});
</script>

<template>
  <section class="featured-card">
    <img class="card-image" :src="image" />
    <div class="card-btm">
      <div class="card-btm-left">
        <p class="title">{{ title }}</p>
        <p class="position">{{ position }}</p>
        <p class="duration">{{ duration }}</p>
        <p class="price-bar">
          <span class="price-">${{ price }}</span> {{ priceUnit }}
        </p>
      </div>
      <div class="card-btm-right">
        <img class="star" src="../images/star.svg" />
        <span class="score">{{ score }}</span>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.featured-card {
  display: flex;
  flex-direction: column;
  gap: 12px;
  cursor: pointer;
  transition: all 200ms ease;

  &:hover {
    .card-image {
      transform: scale(1.03);
    }
  }
}

.card-image {
  width: 302px;
  height: 286px;
  border-radius: 12px;
  object-fit: cover;
  transition: all 200ms ease-in-out;
}

.card-btm {
  display: flex;
  gap: 12px;
  justify-content: space-between;

  &-right {
    height: 20px;
    display: flex;
    align-items: center;
    gap: 4px;
  }
}

.title {
  color: #222;
  font-size: 15px;
  font-weight: 600;
  line-height: 19px;
}

.position {
  color: #717171;
  margin-top: 2px;
  font-size: 15px;
  line-height: 19px;
}

.duration {
  color: #717171;
  margin-top: 2px;
  font-size: 13px;
  line-height: 19px;
}

.price-bar {
  margin-top: 8px;
  display: flex;
  align-items: center;
  gap: 4px;
  color: #222;
  font-size: 15px;
  line-height: 19px;
}

.price {
  font-weight: 600;
}
</style>
