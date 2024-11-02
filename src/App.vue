<script setup>
import MainScreen from './components/MainScreen.vue';
import SubPageScreen from './components/SubPageScreen/SubPageScreen.vue'
import Header from './components/Header.vue'

import { ref,computed } from 'vue';

const routes = {
  '/': MainScreen,
  '/sub-page': SubPageScreen
}

const currentPage = ref(window.location.pathname)

window.addEventListener('popstate', () => {
  console.log(window.location)
  currentPage.value = window.location.pathname
})

const currentView = computed(() => {
  return routes[currentPage.value]
})
</script>

<template>
  <Header/>
  <component :is="currentView"/>
</template>

<style>

</style>
