<script setup>
import ImageShanghai from '../images/inspiration/shanghai.png';
import ImageTemples from '../images/inspiration/temples.png';
import ImageDance from '../images/inspiration/dance.png';

const mainCard = {
  image: ImageShanghai,
  title: 'See the most beautiful night view of Shanghai',
  description: 'Take a walk by the river and go to the bar for a cocktail',
};

const cards = [
  {
    image: ImageTemples,
    title: 'Top five temples in China',
    description: 'Making a wish here is very effective. And too many tourists like these temples.',
  },
  {
    image: ImageDance,
    title: 'The popular ancient villages ',
    description: 'Enjoy ancient Chinese wisdom together! You will experience the beautiful culture in national dress',
  },
];
</script>

<template>
  <section class="inspiration-activities">
    <h2>Inspiration and Activities</h2>
    <div class="cards">
      <HomeInspirationMainCard v-bind="{ ...mainCard }" />
      <HomeInspirationCard v-for="item in cards" v-bind="{ key: item.title, ...item }" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
.inspiration-activities {
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
