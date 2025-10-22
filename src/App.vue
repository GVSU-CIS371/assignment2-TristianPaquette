<template>
  <div>
    <Beverage
      :isIced="currentTemp === 'Cold'"
      :base="base"
      :creamer="creamer"
      :syrup="syrup"
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
    </ul>

    <ul class="options-row">
      <li>
        <label>
          <input type="radio" name="base" value="Black Tea" v-model="base" />
          Black Tea
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="base" value="Green Tea" v-model="base" />
          Green Tea
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="base" value="Coffee" v-model="base" />
          Coffee
        </label>
      </li>
    </ul>

    <ul class="options-row">
      <li>
        <label>
          <input type="radio" name="creamer" value="No Creamer" v-model="creamer" />
          No Cream
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="creamer" value="Milk" v-model="creamer" />
          Milk
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="creamer" value="Cream" v-model="creamer" />
          Cream
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="creamer" value="Half & Half" v-model="creamer" />
          Half & Half
        </label>
      </li>
    </ul>

    <ul class="options-row">
      <li>
        <label>
          <input type="radio" name="syrup" value="No Syrup" v-model="syrup" />
          No Syrup
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="syrup" value="Vanilla" v-model="syrup" />
          Vanilla
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="syrup" value="Caramel" v-model="syrup" />
          Caramel
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="syrup" value="Hazelnut" v-model="syrup" />
          Hazelnut
        </label>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp } from "./stores/beverage";
import { ref } from "vue";

const base = ref("Coffee");
const creamer = ref("No Creamer");
const syrup = ref("No Syrup");
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
// shows bullet points in rows
.options-row {
  display: flex;
  gap: 0.75rem;
  flex-wrap: wrap;
  margin: 0.25rem 0;
}
</style>
