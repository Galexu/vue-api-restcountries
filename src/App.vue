<script setup>
import { ref } from 'vue';

// const nombre = ref('Juan');
// const nombre = ref([]);
// nombre.value = 'Luis';


const urlApi = 'https://restcountries.com/v3.1/region/europe';

function recibirCountries() {
  fetch(urlApi)
  .then((respuesta) => respuesta.json())
  .then((data) => {
    console.log(data)
    countries.value = data;
  })
}

recibirCountries();

const countries = ref([]);
</script>

<template>
  {{ countries }}
</template>
