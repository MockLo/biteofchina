<script setup>
import { NIcon, NDropdown, NConfigProvider } from 'naive-ui';
import { LanguageOutlined, FileUploadOutlined, AccountCircleOutlined } from '@vicons/material';

const router = useRouter();
const submitOptions = [
  {
    label: 'Submit a product',
    key: 'submit',
    path: '/product/submit',
  },
  {
    label: 'Manage products',
    key: 'manage',
    path: '/product/manage',
  },
];
const handleSelect = key => {
  if (!key) return;
  const item = submitOptions.find(x => x.key === key);
  if (!item) return;
  router.push({ path: item.path });
};
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
      <NConfigProvider namespace="submit-dropdown">
        <NDropdown :trigger="'click'" size="huge" :options="submitOptions" @select="handleSelect">
          <NIcon size="28" :component="FileUploadOutlined" />
        </NDropdown>
      </NConfigProvider>
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

  & > .n-config-provider {
    display: flex;
    align-items: center;
  }

  .n-icon {
    color: #d9d9d9;
    cursor: pointer;
    transition: all ease 200ms;

    &:hover {
      color: #fff;
    }
  }
}
</style>
