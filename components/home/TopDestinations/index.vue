<script setup>
import ImageBeijing from '../images/destination/beijing.png';
import ImageShanghai from '../images/destination/shanghai.png';
import ImageGuangzhou from '../images/destination/guangzhou.png';
import ImageXian from '../images/destination/xian.png';
import ImageDali from '../images/destination/dali.png';
import ImageXizang from '../images/destination/xizang.png';
import ImageSichuan from '../images/destination/sichuan.png';
import ImageFuzhou from '../images/destination/fuzhou.png';

const cards = [
  {
    image: ImageBeijing,
    city: 'Beijing',
  },
  {
    image: ImageShanghai,
    city: 'Shanghai',
  },
  {
    image: ImageGuangzhou,
    city: 'Guizhou',
  },
  {
    image: ImageXian,
    city: 'Xian',
  },
  {
    image: ImageDali,
    city: 'Dali',
  },
  {
    image: ImageXizang,
    city: 'Xizang',
  },
  {
    image: ImageSichuan,
    city: 'Sichuan',
  },
  {
    image: ImageFuzhou,
    city: 'Fuzhou',
  },
];
</script>

<template>
  <section class="top-destinations">
    <h2>Top Destinations</h2>
    <div class="cards">
      <HomeTopDestinationsCard v-for="item in cards" v-bind="{ key: item.city, ...item }" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.top-destinations {
  display: flex;
  flex-direction: column;
  gap: 30px;

  & > h2 {
    color: #000;
    font-size: 40px;
    font-weight: 800;
  }
}

.cards {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 30px 0;
}
</style>
