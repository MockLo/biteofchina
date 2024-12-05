<script setup>
import CardImage1 from '../images/card-1.png';
import CardImage2 from '../images/card-2.png';
import CardImage3 from '../images/card-3.png';
import CardImage4 from '../images/card-4.png';

const cards = [
  {
    image: CardImage1,
    title: 'Experience ancient village culture',
    position: 'Guilin, GuangXi Province',
    duration: '3 days Trip',
    price: '388',
    priceUnit: 'per adult',
    score: '5.0',
  },
  {
    image: CardImage2,
    title: 'JiaXing, Four days Trip',
    position: 'JiaXing, ZheJiang Province',
    duration: '4 days Trip',
    price: '343',
    priceUnit: 'per adult',
    score: '4.93',
  },
  {
    image: CardImage3,
    title: 'Guizhou, 7 days Trip',
    position: 'Mountain views',
    duration: 'Apr 30 – May 5',
    price: '388',
    priceUnit: 'per adult',
    score: '5.0',
  },
  {
    image: CardImage4,
    title: 'Beijing, 2 days Trip',
    position: 'City views',
    duration: 'Apr 4 – 9',
    price: '326',
    priceUnit: 'night',
    score: '4.72',
  },
];
</script>

<template>
  <section class="featured-package">
    <h2>Featured Package</h2>
    <div class="cards">
      <HomeFeaturedPackageCard v-for="item in cards" v-bind="{ key: item.title, ...item }" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.featured-package {
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
}
</style>
