<template>
  <div class="h-screen grid place-items-center">
    <div
      class="h-[700px] w-[375px] overflow-y-auto rounded-[30px] shadow-lg border border-gray-300 bg-white"
    >
      <templates-simple :acc="data" />
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  data: {
    type: Object,
    required: true,
  },
});
</script>
<style scoped></style>
