<script setup>
const props = defineProps({
  image: { type: String, default: '' },
  city: { type: String, default: '' },
});
</script>

<template>
  <section class="destination-card">
    <img :src="image" />
    <div class="card-top">
      <p class="city">{{ city }}</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.destination-card {
  position: relative;
  display: flex;
  width: 290px;
  height: 162px;
  border-radius: 12px;
  overflow: hidden;
  cursor: pointer;
  transition: all 200ms ease;

  & > img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 16px;
  }

  &:hover {
    transform: scale(1.04);

    .city {
      transform: scale(1.2);
    }
  }
}

.card-top {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 24px;
  background: rgba(0, 0, 0, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
}

.city {
  color: #fff;
  font-size: 25px;
  font-weight: 700;
  line-height: normal;
  transition: all 200ms ease;
}
</style>
