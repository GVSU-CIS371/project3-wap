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
      <h3>Temperature</h3>
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
      <h3>Creamer</h3>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer }}
          </label>
        </template>
      </li>
      <li>
      <h3>Syrup</h3>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup }}
          </label>
        </template>
      </li>
      <li>
      <h3>Base Beverage</h3>
        <template v-for="base in bases" :key="base">
          <label>
            <input
              type="radio"
              name="base"
              :id="`r${base}`"
              :value="base"
              v-model="currentBase"
            />
            {{ base }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
// Define reactive data
const temps = ref(["Hot", "Cold"]);
const currentTemp = ref("Hot");

const creamers = ref(["None", "Milk", "Cream", "Half & Half"]);
const currentCreamer = ref("None");

const syrups = ref(["None", "Vanilla", "Caramel", "Hazelnut"]);
const currentSyrup = ref("None");

const bases = ref(["Coffee", "Green Tea", "Black Tea"]);
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
