<template>
  <div class="flex flex-col items-center justify-center min-h-screen">
    <templates-simple v-if="decodedData" :acc="decodedData" />
    <div
      v-else
      class="flex items-center justify-center h-full w-full"
    >
      <base-loading class="h-5 w-5" />
    </div>
  </div>
</template>
<script setup>
import { decodeData } from "../utils/transformer";
const route = useRoute();
const acc = route.query.data;
const decodedData = ref({});
decodedData.value = decodeData(acc);
</script>
<style scoped>
@media (max-width: 640px) {
  .h-5 {
    height: 2rem; /* Adjust size for smaller screens */
    width: 2rem; /* Adjust size for smaller screens */
  }
}
</style>
