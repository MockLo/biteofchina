<script setup>
import { NCarousel, NIcon } from 'naive-ui';
import { LocationOnOutlined } from '@vicons/material';
import BgHangzhou from './images/image_35.png';
import BgJingdezhen from './images/image_47.png';
import BgAI from './images/image_AI.png';

const items = [
  {
    city: 'Hangzhou',
    desc: 'Pick tea  beside the West Lake',
    title: 'New Travel Paradigm',
    image: BgHangzhou,
    slogan: 'Authentic Travel Experiences',
  },
  {
    city: 'Jingdezhen',
    desc: 'Make porcelain',
    title: 'New Travel Paradigm',
    image: BgJingdezhen,
    slogan: 'Culture Based Experiences ',
  },
  {
    title: 'New Travel Paradigm',
    slogan: 'Your AI Assistant is always online for you ',
    image: BgAI,
    disableBook: true,
  },
];
</script>

<template>
  <div class="carousel">
    <NCarousel draggable autoplay>
      <div class="carousel-item" v-for="item in items" :key="item.city">
        <img class="carousel-bg" :src="item.image" />
        <div class="top-layer">
          <div class="main-title">
            <p class="title">{{ item.title }}</p>
            <p class="slogan">{{ item.slogan }}</p>
          </div>

          <div v-if="item.city" class="position">
            <div class="city">
              <NIcon size="30" :component="LocationOnOutlined" color="#fff" />
              <span>{{ item.city }}</span>
            </div>
            <p v-if="item.desc" class="desc">{{ item.desc }}</p>
          </div>

          <div v-if="!item.disableBook" class="book-btn" role="button">Book it Now!</div>
        </div>
      </div>
    </NCarousel>
  </div>
</template>

<style lang="scss" scoped>
.carousel {
  width: 100%;
  height: 634px;
  overflow: hidden;

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
}

.main-title {
  margin-top: 164px;
  text-align: center;
}

.title {
  color: #fff;
  font-size: 50px;
  font-weight: 700;
}

.slogan {
  color: #fff;
  font-size: 70px;
  font-weight: 800;
  line-height: normal;
  margin-top: 20px;
}

.position {
  position: absolute;
  left: 40px;
  bottom: 40px;
}

.city {
  display: flex;
  align-items: center;
  gap: 10px;
  line-height: normal;

  & > span {
    color: #fff;
    font-size: 30px;
    font-weight: 800;
  }
}

.desc {
  margin-top: 10px;
  font-size: 20px;
  color: #dfdfdf;
  font-weight: 800;
  text-decoration: underline;
}

.book-btn {
  position: absolute;
  right: 40px;
  bottom: 40px;
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
</style>
