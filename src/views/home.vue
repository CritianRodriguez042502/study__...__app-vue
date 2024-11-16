<script setup>
import { ref } from 'vue';

const newInfo = ref('Hello');
const counter = ref(0);

const names = [{ name: "Cristian", age: 23 }, { name: "Juan", age: 24 }, { name: "Pedro", age: 25 }, { name: "Camilo", age: 17 }];

function changeText() {
  if (newInfo.value === "Hello") {
    newInfo.value = "Hello_1"
  } else {
    newInfo.value = "Hello_" + `${parseInt(newInfo.value.split("_")[1]) + 1}`
  }
}


const increment = () => {
  counter.value = counter.value + 1;
}


const conditional = ref(true);
const otherConditional = ref(false);

function changeInfo() {
  conditional.value = !conditional.value;
}

</script>

<template>
  <h1 v-text="newInfo" @click="changeText" :id="$style.title"></h1>
  <p>Counter: {{ counter }}</p>
  <button @click="increment">Increment</button>
  <p :class="$style.fontWeight"> Cero</p>

  <p v-if="conditional"> this is awesome</p>
  <p v-else> Oh no!</p>
  <button @click="changeInfo"> Toggle </button>


  <h2 v-show="otherConditional"> Informacion </h2>

  <div v-for="user of names"> 
    <h1 :class="$style.smallSize" v-show="user.age > 18"> {{ user.name }}</h1>
  </div>
</template>

<style module>
#title {
  color: red;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}

.fontSize {
  font-size: 60px;
}

.smallSize {
  font-size: 10px
}

.greenColor {
  color: green;
}

.fontWeight {
  font-weight: 100
}
</style>