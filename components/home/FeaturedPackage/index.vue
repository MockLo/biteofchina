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
    duration: 'one day Trip',
    price: '99',
    priceUnit: 'per adult',
    score: '5.0',
  },
  {
    image: CardImage2,
    title: 'Find healing in the temple',
    position: 'Guoqing Temple, ZheJiang Province',
    duration: '2 days Trip',
    price: '399',
    priceUnit: 'per adult',
    score: '4.93',
  },
  {
    image: CardImage3,
    title: 'Dumpling lesson',
    position: 'Shanghai',
    duration: 'half day Activity',
    price: '50',
    priceUnit: 'per adult',
    score: '5.0',
  },
  {
    image: CardImage4,
    title: 'Feel ancient China',
    position: 'Beijing',
    duration: 'two days Trip',
    price: '326',
    priceUnit: 'per adult',
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
