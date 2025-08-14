<script setup lang="ts">
const items = [
  'https://picsum.photos/468/468?random=1',
  'https://picsum.photos/468/468?random=2',
  'https://picsum.photos/468/468?random=3',
  'https://picsum.photos/468/468?random=4',
  'https://picsum.photos/468/468?random=5',
  'https://picsum.photos/468/468?random=6'
];
</script>
  <!-- eslint-disable vue/no-multiple-template-root -->

<template>
  <section>
    <AppHero />
  </section>

  <!-- <section class="flex flex-row">
    <h2>Choose now</h2>
    <div>
      <a href="/">T-shirts</a>
      <a href="/">Embroidery</a>
      <a href="/">Aprons</a>
      <a href="/">Baby-clothing</a>
      <a href="/">Mugs</a>
    </div>
  </section> -->

  <section>
    <h2>Bestsellers</h2>
    <UCarousel
      v-slot="{ item }"
      arrows
      :items="items"
      :ui="{ item: 'basis-1/4' }"
    >
      <img :src="item" class="rounded-lg" />
    </UCarousel>
  </section>
</template>
