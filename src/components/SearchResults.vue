<script setup>
import { computed } from '@vue/reactivity';
import titles from '../assets/post-data.json';
const props = defineProps({
    query: String
})
const filteredTitles = computed(() => {
    return titles.filter(t => t.Name.toLowerCase().includes(props.query.toLowerCase()))
})
</script>

<template>
    <div class="root">
        <p>Showing {{ filteredTitles.length }} results for "{{ query }}"</p>
        <ul>
            <li v-for="title in filteredTitles" :key="title.Page">
                <a v-bind:href="title.Page">{{ title.Name }}</a>
            </li>
        </ul>
    </div>
</template>