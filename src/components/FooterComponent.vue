<template>
    <footer class="mt-5 p-3 bg-dark text-white text-center">
        © {{ year }} 李岳峰個人簡歷 All rights reserved.
    </footer>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const year = ref(0);
onMounted(() => year.value = new Date().getFullYear());
</script>