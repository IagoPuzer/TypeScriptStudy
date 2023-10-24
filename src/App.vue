<script setup lang="ts">
import { ref } from "vue";
import PersonsList from "./components/PersonsList.vue";
import type { PersonInterface } from "./types/Person";

let age = ref(40);

let persons = ref<PersonInterface[]>([
  {
    id: 0,
    name: "iago",
    age: 27,
  },
  {
    id: 1,
    name: "Joyce",
    age: 24,
  },
  {
    id: 2,
    name: "Clara",
    age: 21,
  },
]);

const changeAge = (newAge: number) => {
  age.value = newAge;
};

interface AddressInterface {
  number: number | string;
  street: string;
}

interface DataInterface {
  name: string;
  age: number | string;
  address: AddressInterface;
  isAdult: boolean;
}

const data: DataInterface = {
  name: "Iago",
  age: 27,
  address: {
    number: "23",
    street: "My Street",
  },
  isAdult: true,
};

const image = ref("image.png");
</script>

<template>
  <div>
    <img :src="image" alt="" />
  </div>

  <div style="margin-bottom: 20px">My age {{ data.age }}</div>

  {{ age }}
  <button @click="changeAge(20)">change age</button>

  <PersonsList :persons="persons" />
</template>

<style scoped></style>
