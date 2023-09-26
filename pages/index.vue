<script setup>
import { onMounted, ref } from 'vue';
import { useRouter } from 'vue-router';

onMounted(() => {
    const router = useRouter();
    router.push({ path: '/frontend/frameworks/vue' });
});
</script>

<template></template>
