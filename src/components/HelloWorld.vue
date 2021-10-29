<script setup>
import { ref } from 'vue';
import SearchResults from './SearchResults.vue';

// defineProps({
//   msg: String
// })

const query = ref('')
const reset = () => {
  query.value = '' // clears the query
}
</script>

<template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <p>{{ query }}</p>
    <button v-on:click="reset">Reset</button>
    <SearchResults v-bind:query="query" />
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
