<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />

    <Contents>
      // top row, Creamer if chosen, otherwise Syrup if chosen
      <template v-slot:top>
        <Creamer v-if="creamer !== 'No Creamer'" :type="creamer" />
        <Syrup v-else-if="syrup !== 'No Syrup'" :type="syrup" />
      </template>

      // middle row, only used when both creamer and syrup are chosen
      <template v-slot:mid>
        <Syrup v-if="creamer !== 'No Creamer' && syrup !== 'No Syrup'" :type="syrup" />
      </template>

      // bottom row, base
      <template v-slot:bottom>
        <Base :type="base" />
      </template>
    </Contents>
  </Mug>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
  base?: string;
  creamer?: string;
  syrup?: string; 
};
const props = defineProps<Props>()
</script>

