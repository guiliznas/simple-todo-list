<script setup>
import { reactive } from "vue";

const tasks = reactive([
  {
    desc: "",
    id: 1,
  },
  {
    desc: "",
    id: 2,
  },
  {
    desc: "",
    id: 3,
  },
  {
    desc: "",
    id: 4,
  },
  {
    desc: "",
    id: 5,
  },
]);
</script>

<template>
  <div style="display: flex; flex-direction: column; gap: 8px;">
    <template v-for="task in tasks" :key="task.id">
      <input v-model="task.desc" placeholder="Tarefas" />
    </template>
  </div>
</template>
