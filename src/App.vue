<template>
  <div>
    
<Beverage
  :isIced="currentTemp === 'Cold'"
  :creamer="currentCreamer"
  :syrup="currentSyrup"
  :base="currentBase"
/>

    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>


<li>
  <label for="creamer">Creamer:</label>
  <select id="creamer" v-model="currentCreamer">
    <option v-for="creamer in creamers" :key="creamer">
      {{ creamer }}
    </option>
  </select>
</li>

<li>
  <label for="syrup">Syrup:</label>
  <select id="syrup" v-model="currentSyrup">
    <option v-for="syrup in syrups" :key="syrup">
      {{ syrup }}
    </option>
  </select>
</li>

<li>
  <label for="base">Base Beverage:</label>
  <select id="base" v-model="currentBase">
    <option v-for="base in bases" :key="base">
      {{ base }}
    </option>
  </select>
</li>

    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";


import { ref } from "vue";

const creamers = ["No Creamer", "Milk", "Cream", "Half & Half"];
const syrups = ["No Syrup", "Vanilla", "Caramel", "Hazelnut"];
const bases = ["Coffee", "Green Tea", "Black Tea"];

const currentCreamer = ref("No Creamer");
const currentSyrup = ref("No Syrup");
const currentBase = ref("Coffee");

</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
