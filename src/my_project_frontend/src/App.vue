<script setup>
import { ref } from 'vue';
import { my_project_backend } from 'declarations/my_project_backend/index';

let greeting = ref('');

const getDataFromNBP = async () => {
  try {
    const res = await fetch("https://api.nbp.pl/api/exchangerates/tables/A/?format=json");
    if (!res.ok) {
      throw new Error(`HTTP error! status: ${res.status}`);
    }
    const jsonData = await res.json();
    console.log(jsonData);
  } catch (error) {
    console.error('Error fetching data from NBP:', error);
  }
};


getDataFromNBP();
</script>

<template>
  <main>
    <img src="/logo2.svg" alt="DFINITY logo" />
    <br />
    <br />
  </main>
</template>