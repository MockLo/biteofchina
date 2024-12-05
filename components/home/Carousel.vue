<script setup>
import Flicking from '@egjs/vue3-flicking';
import { AutoPlay, Pagination } from '@egjs/flicking-plugins';
import '@egjs/vue3-flicking/dist/flicking.css';
import '@egjs/flicking-plugins/dist/flicking-plugins.css';
import BgGuiLin from './images/image_35.png';
import BgSuZhou from './images/image_12.png';
import BgXinJiang from './images/image_27.png';

const items = [
  {
    city: 'GuiLin',
    slogan: 'Authentic Travel Experiences',
    title: 'New Travel Paradigm',
    image: BgGuiLin,
  },
  {
    city: 'SuZhou',
    slogan: 'Authentic Travel Experiences',
    title: 'New Travel Paradigm',
    image: BgSuZhou,
  },
  {
    city: 'XinJiang',
    slogan: 'Authentic Travel Experiences',
    title: 'New Travel Paradigm',
    image: BgXinJiang,
  },
];

const plugins = [new AutoPlay({ duration: 3000, stopOnHover: true }), new Pagination({ type: 'bullet' })];
</script>

<template>
  <div class="carousel">
    <Flicking :options="{ circular: true }" :plugins="plugins">
      <div class="carousel-item" v-for="item in items" :key="item.city">
        <img class="carousel-bg" :src="item.image" />
        <div class="top-layer">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-city">{{ item.city }}</p>
          <p class="item-slogan">{{ item.slogan }}</p>

          <div class="book-btn" role="button">Book it Now!</div>
        </div>
      </div>

      <template #viewport>
        <div class="flicking-pagination" />
      </template>
    </Flicking>
  </div>
</template>

<style lang="scss" scoped>
.carousel {
  width: 100%;

  &-item {
    width: 100%;
    height: 634px;
    position: relative;
    display: flex;
  }

  &-bg {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.top-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  right: 0;
  bottom: 0;
  padding: 38px 62px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  justify-content: flex-end;
}

.item {
  &-title {
    color: #000;
    font-size: 50px;
    font-weight: 700;
    text-align: center;
    width: 100%;
  }

  &-city {
    margin-top: 70px;
    text-align: right;
    color: #fff;
    font-size: 70px;
    font-weight: 800;
    line-height: normal;
  }

  &-slogan {
    text-align: right;
    color: #fff;
    font-size: 70px;
    font-weight: 800;
    line-height: normal;
  }
}

.book-btn {
  margin-top: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 22px 54px;
  border-radius: 40px;
  background-color: rgba(248, 248, 248, 0.24);
  color: #000;
  font-size: 20px;
  font-weight: 800;
  cursor: pointer;
  transition: all ease 200ms;

  &:hover {
    background-color: #fff;
  }
}

.flicking-pagination {
  &:deep(.flicking-pagination-bullet) {
    width: 10px;
    height: 10px;
    margin: 0 6px;
    background-color: rgba(#f8f8f8, 0.24);
    transition: all 200ms ease;
  }

  &:deep(.flicking-pagination-bullet-active) {
    background-color: #fff;
  }
}
</style>
