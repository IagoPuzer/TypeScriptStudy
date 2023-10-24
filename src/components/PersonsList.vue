<template>
  <div>
    <h2>Users List</h2>
    <div>
      <ul>
        <li v-for="persons in props.persons" :key="persons.id">
          {{ persons.age }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { PropType } from "vue";
import type { PersonInterface } from "../types/Person";

const props = defineProps({
  persons: {
    required: true,
    type: Array as PropType<PersonInterface[]>,
  },
});
</script>

<style scoped></style>
