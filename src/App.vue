<script setup lang="ts">
import { RouterView } from 'vue-router'
import NavBarComponent from '@/components/NavBar.vue'
</script>

<template>
  <div class="layout w-full h-full relative">
    <NavBarComponent class="header" />
    <div class="main grid grid-nogutter z-auto">
      <div class="col-fixed align-content-center" style="width: 30px">
        <button class="button bg-primary-reverse border-none" type="button">
          <i class="pi pi-angle-left" style="font-size: 2rem"></i>
        </button>
      </div>
      <main class="col">
        <RouterView />
      </main>
      <div class="col-fixed align-content-center" style="width: 30px">
        <button class="button bg-primary-reverse border-none" type="button">
          <i class="pi pi-angle-right" style="font-size: 2rem"></i>
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.layout {
  display: grid;
  grid:
    'header' auto
    'main' 1fr
    '.' auto
    / 1fr;

  .header {
    grid-area: header;
  }
  .main {
    grid-area: main;

    .button {
      &:hover,
      &:focus {
        transform: scale(1.2);
        transition: all 0.2s;
      }
    }
  }
}
</style>
