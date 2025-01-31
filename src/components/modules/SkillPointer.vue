<template>
    <span class="badge fs-6 fst-italic text-bg-light text-secondary m-1">{{ props.name }}</span> 
</template>

<script setup>
import { defineProps } from 'vue';
const props = defineProps(['name']);
</script>