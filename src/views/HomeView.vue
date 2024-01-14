<script setup>
import { onMounted, ref } from "vue";

let jobs = ref([]);
onMounted(() => {
  console.log("hell");
  fetch("http://localhost:3000/jobs")
    .then((res) => res.json())
    .then((data) => (jobs.value = data));
});
</script>

<template>
  <h1></h1>
  <div v-if="jobs">
    <div v-for="jobs in jobs">
      <span>name {{ jobs.title }}</span>
    </div>
  </div>
</template>

<style></style>
