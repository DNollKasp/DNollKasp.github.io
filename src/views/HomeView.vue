<script setup lang="ts">
import Shecdule from '@/components/Shecdule.vue';
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main>
    <TheWelcome />
    <Shecdule />
    <a href="/pr">

      <img src="/giga-hacke-Bm5F8_ez.png" alt="">
    </a>
  </main>
</template>


<style scoped>

main {
  position: relative;
}

img {
  width: 250px;
}

a {
  position: absolute;
  bottom: -100px;
  left: 50px
}
</style>