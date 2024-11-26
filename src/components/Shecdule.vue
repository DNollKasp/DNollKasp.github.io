<template>
  <h2>
    Schema för Minimottagningen
  </h2>
    <p>
        Här kan du se schemat för Minimottagningen
    </p>


    <div class="outer-schema">
    <div class="schema">
        <div class="headish">
    <h3>12/1</h3>
</div>


    <li v-for="item in items" >
    <button @click="item.show= true">
      <div class="item">
    {{ item.namn }}
  </div>
  </button>
    <Teleport to="body">
    <!-- use the modal component, pass in the prop -->
    <modal :show="item.show" @close="item.show = false">
      <template #image>
        <img v-bind:src="item.src" alt="" class="image">
      </template>
      <template #header>
        <h3>{{ item.namn }}</h3>
      </template>
      <template #body>
        <h3>{{ item.desc }}</h3>
        <div class="box">
          <svg class="icon" data-v-2836fdb5-s="" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon"><path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path><path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1 1 15 0Z"></path></svg>
          <a v-bind:href="item.plats.link">{{ item.plats.namn }}</a>
        </div>
        <div class="box">
          <svg data-v-2836fdb5-s="" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true" data-slot="icon" class="icon"><path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"></path></svg>
          <p>{{ item.start }}</p>
        </div>
      </template>
    </modal>
    </Teleport>
    </li>
    </div>
</div>


</template>

<script setup lang="ts">
import Modal from './Modal.vue'


import { defineComponent, ref } from 'vue';

const showModal = ref(false)

const items = ref([
{ namn: 'Första dagen', show: false, src: "/preview.webp", alt: "", desc: "Här börjar äventyret. kom inte sent!", start: "10:01", plats: {namn: "Teknologgården", link: "https://maps.chalmers.se/#e61e2b38-a795-44cf-b973-c68a4305e65a"} },
{ namn: 'Nollbrickstillverkning', show: false, src: "/preview2.webp", alt: "", desc: "Det är dags att skapa din viktigaste ägodel inför mottagningnen! Kom med ett glatt humör och ge inte upp!", start: "10:31", plats: {namn: "Vindgården", link: "https://maps.chalmers.se/#1a220220-04b9-11ec-8ac8-af7b728407b9"} },
{ namn: 'Lunchföreläsning', show: false, src: "", alt: "", desc: "tbc", start: "11:31", plats: {namn: "Basen", link: "https://maps.chalmers.se/#6967eb7c-ff54-4dd7-af00-9e19fcaba128"} },
{ namn: '∆-dagen', show: false, src: "/preview3.webp", alt: "", desc: "Lär dig att häfva med Delta.", start: "12:01", plats: {namn: "∆-parken", link: "https://maps.chalmers.se/#1a220220-04b9-11ec-8ac8-af7b728407b9"} },
{ namn: 'Suprise???', show: false, src: "", alt: "", desc: "Ta med er badkläder + handuk är allt ni får veta", start: "13:01", plats: {namn: "???", link: ""} },
{ namn: 'Gasque', show: false, src: "/preview4.webp", alt: "", desc: "Nu ska vi Gasqua, var [fill in the blank] är min flaska?", start: "16:16", plats: {namn: "Gasquen", link: ""} },
{ namn: 'Finsittning', show: false, src: "/preview5.webp", alt: "", desc: "Här kommer ni få en fantastisk sittning", start: "17:31", plats: {namn: "Basen", link: "https://maps.chalmers.se/#6967eb7c-ff54-4dd7-af00-9e19fcaba128"} }

])
defineComponent({
  name: 'Shecdule',
});

</script>

<style scoped>

.box {
  display: flex;
  align-items: center;
  flex-direction: row;
  margin-top: 0.5rem;}

.box p {
  font-size: 1rem;
  margin-top: 0px;
}

.icon {
  width: 1.5rem;
  height: 1.5rem;
  margin-right: 0.5rem;
}

* {
  color: white;
}

.image {
  width: 100%;
  border-radius: 10px 10px 0px 0px;
}

button {
  width: 100%;
  background: none;
	color: inherit;
	border: none;
	padding: 0;
	font: inherit;
	cursor: pointer;
	outline: inherit;
}

li {
  width: 100%;
  list-style-type: none;
}

.headish {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  border-radius: 10px 10px 0px 0px;
  width: 100%;
  background-color: #858585;
  border: 2px solid #858585;
}

.item {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin: 10px;
  padding: 10px;
  border-radius: 10px;
  width: 98%;
  background-color: #646464;
  border: 2px solid #4e4e4e;
}

.item:hover {
  background-color: #858585;
}

.outer-schema {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
;
}

.schema {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin: 10;
  padding: 10;
  width: 40%;
  border-radius: 10px;
  border: 2px solid #858585;
    background-color: #4e4e4e;
}

h2 {
  font-size: 2.6rem;
  text-align: center;
  margin-top: 2rem;
}

p {
  font-size: 1.2rem;
  text-align: center;
  margin-top: 1rem;
}

</style>



