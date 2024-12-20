<template>
  <main id="main-app">
    <NMessageProvider>
      <NModalProvider>
        <slot />
      </NModalProvider>
    </NMessageProvider>
    <SpeedInsights />
  </main>
</template>

<script setup>
import { SpeedInsights } from '@vercel/speed-insights/nuxt';
import { NMessageProvider, NModalProvider } from 'naive-ui';

const route = useRoute();
useHead({
  title: route.meta.title,
  meta: [{ property: 'og:title', content: `BiteOfChina - ${route.meta.title}` }],
});
</script>

<style lang="scss">
/* Box sizing rules */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/* Remove default margin */
body,
h1,
h2,
h3,
h4,
p,
figure,
blockquote,
dl,
dd {
  margin: 0;
}

/* Remove list styles on ul, ol elements with a list role, which suggests default styling will be removed */
ul[role='list'],
ol[role='list'] {
  list-style: none;
}

/* Set core root defaults */
html:focus-within {
  scroll-behavior: smooth;
}

/* Set core body defaults */
body {
  min-height: 100vh;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
}

/* A elements that don't have a class get default styles */
a:not([class]) {
  text-decoration-skip-ink: auto;
}

/* Make images easier to work with */
img,
picture {
  max-width: 100%;
  display: block;
}

/* Inherit fonts for inputs and buttons */
input,
button,
textarea,
select {
  font: inherit;
}

#main-app {
  min-width: 1440px;
  margin: 0 auto;
}
</style>
