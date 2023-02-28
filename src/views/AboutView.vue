<template>
  <div class="about">
    <!-- <h1>This is an about page</h1> -->
    <p>{{ msg }}</p>
    <p>{{ myArray }}</p>
    <ul>
      <li v-for="item in myArray" :key="item">
        {{ item }}
      </li>
    </ul>
    <ul>
      <li v-for="item in myObject" :key="item.name">
        {{ item.name }}
      </li>
    </ul>
    <button @click="hideShow = !hideShow">Hide/show</button>
    <div v-if="hideShow">
      True
    </div>
    <div v-else>
      False
    </div>
    <div v-show="hideShow">
      True Show
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

let msg = ref("Hello World")
let myArray = ref([1, 2, 3, 4, 5])
let myObject = ref([
  { name: "John", age: 30 },
  { name: "Sara", age: 25 },
  { name: "Jane", age: 20 },
])

let hideShow = ref(false)

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
