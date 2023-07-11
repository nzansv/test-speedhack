<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Sidebar from './components/Sidebar.vue'
import Header from './components/Header.vue'
import Courses from '@/components/Courses.vue'
</script>

<template>
    <Sidebar></Sidebar>
    <RouterView />
</template>

<style scoped>

</style>
