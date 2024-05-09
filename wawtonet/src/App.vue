<template>
  <div id="wrapper">

    <NavBar />
    <div class="container">
      <h3 class="subtitle">Hitro iskanje osebnih vozil</h3>
      <HitroIskanjeForma />

    </div>
    
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import HitroIskanjeForma from './components/HitroIskanjeForma.vue'
const znamke = ["Audi", "BMW", "Citroen", "Ford", "Mercedes-Benz", "Renault", "Škoda", "Volkswagen"]
</script>
<style lang="scss">
@import '../node_modules/bulma/';
</style>
