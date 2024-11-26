<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div id="header">
      
      <img src="./assets/svg (4).svg" alt="" srcset="">

        <nav>
          <RouterLink to="/" activeClass="active">Home</RouterLink>
          <RouterLink to="/about" activeClass="active">About</RouterLink>
        </nav>
    </div>
  </header>
  <RouterView />

  <footer>
    <div class="footer">
    <img src="./assets/svg (4).svg" alt="" srcset="">
    <p>All bildmaterial tillhör <a href="https://dfoto.se">Dfoto</a></p>
  </div>
  </footer>
</template>

<style scoped>

footer {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 70px;
  margin: 50px 0px 0px 0px;
  background-color: rgb(17, 17, 17);
}

.footer {
  display: flex;
  justify-content: space-around;
  align-items: center;
  
  width: 40%;
}

.footer img {
  width: 250px;
}

header {
  height: 70px;
  display: flex;
  justify-content: center;
  background-color: rgb(17, 17, 17);
}

#header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 40%;
}

#header img {
  width: 250px;
  
}

nav{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.active {
  background-color: hwb(22 1% 9%);
}

.active:hover {
  background-color: hwb(22 1% 9%);
}

nav a {
  color: white;
  margin: 0 1rem;
  display: block;
  padding: 0.5rem 1rem;
  text-decoration: none;
  border-radius: 0.5rem;
}

nav a:hover {
  color: white;
  margin: 0 1rem;
  background-color: hwb(0 13% 87%);
  display: block;
  padding: 0.5rem 1rem;
  text-decoration: none;
  border-radius: 0.5rem;
}

</style>
