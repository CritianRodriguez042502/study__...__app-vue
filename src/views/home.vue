<script setup>
import { ref } from "vue";
import { toast } from "vue3-toastify";
import "vue3-toastify/dist/index.css";

const executionClick = ref(false);

function changeDomain() {
  if (!executionClick.value) {
    executionClick.value = true;

    toast.warning("I'm Cristian . . .", {
      position: "top-right",
    });

    toast.success("Redirecting . . .", {
      position: "top-left",
    });

    toast.error("Hello world :)", {
      position: "top-center",
    });

    toast.warning("I'm Cristian . . .", {
      position: "bottom-right",
    });

    toast.success("Redirecting . . .", {
      position: "bottom-left",
    });

    toast.error("Hello world :)", {
      position: "bottom-center",
    });

    window.setTimeout(() => {
      window.location.href = "https://web-portfolio-z9ym.onrender.com";
    }, 3000);
  }
  return;
}
</script>

<template>
  <main class="container">
    <h1 class="home-text" @click="changeDomain()">Click here</h1>
  </main>
</template>

<style scoped>
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.home-text {
  color: gray;
  cursor: pointer;
  text-decoration: underline;
  font-weight: 900;
}
</style>
