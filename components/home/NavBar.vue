<script setup>
import { NIcon, NTooltip } from 'naive-ui';
import { LanguageOutlined, FileUploadOutlined, AccountCircleOutlined } from '@vicons/material';
</script>

<template>
  <nav class="home-nav-bar">
    <img class="nav-logo" src="./images/boc-logo.png" />
    <div class="sub-menus">
      <div class="sub-menu">Activities</div>
      <div class="sub-menu">Inspiration</div>
      <div class="sub-menu">AI Assistant</div>
    </div>
    <div class="right-btns">
      <NIcon size="28" :component="LanguageOutlined" />
      <NTooltip>
        <template #trigger>
          <NIcon size="28" :component="FileUploadOutlined" />
        </template>
        Submit Your Product
      </NTooltip>
      <NIcon size="28" :component="AccountCircleOutlined" />
    </div>
  </nav>
</template>

<style lang="scss" scoped>
.home-nav-bar {
  position: absolute;
  width: 100%;
  height: 60px;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.25);
  display: flex;
  align-items: center;
  padding: 0 32px;
  z-index: 2;
}

.nav-logo {
  width: auto;
  height: 46px;
}

.sub-menus {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 56px;
  margin-left: auto;
}

.sub-menu {
  color: #d9d9d9;
  font-size: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all ease 200ms;

  &:hover {
    color: #fff;
  }
}

.right-btns {
  margin-left: 124px;
  display: flex;
  align-items: center;
  gap: 15px;

  & > .n-icon {
    color: #d9d9d9;
    cursor: pointer;
    transition: all ease 200ms;

    &:hover {
      color: #fff;
    }
  }
}
</style>
