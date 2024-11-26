<template>
  <div :style="backgroundStyle" class="welcome">
    <div>
    <img src="../assets/dnollk-patch-jxXtwMoP.png" alt="" srcset="" >
    <h2>Välkomen till Minimottagningen!</h2>
    <p>Bästa arret efter den riktiga mottagningen</p>
  </div>
  </div>
</template>

<script lang="ts">

import WelcomeItem from './Shecdule.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
import { defineComponent, onMounted, onBeforeUnmount, ref, computed } from 'vue';

export default defineComponent({
  setup() {
    const currentImageIndex = ref<number>(0);
    const images = ref<string[]>([
      '/rolling/fullSize.webp',
      '/rolling/fullSize1.webp',
      '/rolling/fullSize2.webp',
      '/rolling/fullSize3.webp',
      // Add more images as needed
    ]);
    let intervalId: number | undefined;

    const backgroundStyle = computed(() => (
      console.log('Computed backgroundStyle'),
      console.log(images.value[currentImageIndex.value]),
    {
      backgroundImage: `url(${images.value[currentImageIndex.value]})`,
      backgroundSize: 'cover',
      backgroundPosition: 'center',
      width: '100%',
      height: '90vh', // Adjust height as needed
    }));

    const rotateImage = () => {
      //console.log('Rotating image');
      //console.log(currentImageIndex.value);
      currentImageIndex.value = (currentImageIndex.value + 1) % images.value.length;
    };

    const startImageRotation = () => {
      intervalId = window.setInterval(rotateImage, 15000);
    };

    const stopImageRotation = () => {
      if (intervalId !== undefined) {
        clearInterval(intervalId);
      }
    };

    onMounted(() => {
      startImageRotation();
    });

    onBeforeUnmount(() => {
      stopImageRotation();
    });

    return {
      currentImageIndex,
      images,
      backgroundStyle,
    };
  },
});
</script>

<style scoped>
.welcome {
  width: 100%;
  height: 90vh;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
}

.welcome div {
  display: flex;
  flex-direction: column;
  align-items: center;

}

.welcome div img {
  width: 250px;
}

h2 {
  font-size: 2rem;
  color: white;
  text-align: center;
  font-weight: 900;
  font-size: 4.5rem;
  opacity: 1;
  font-family: macho, sans-serif;
}
</style>