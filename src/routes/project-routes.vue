<script setup>
import { ref, computed } from "vue";

// Import Views
import Home from "../views/home.vue";
import About from "../views/about.vue";
import NotFound from "../components/errors/not-found.vue";

const routes = {
  "/": Home,
  "/home": Home,
  "/about": About,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] || NotFound;
});
</script>

<template>
  <component :is="currentView" />
</template>

<style scoped></style>
