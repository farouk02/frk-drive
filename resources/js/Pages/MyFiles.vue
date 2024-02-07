<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue'
</script>
<template>
    <AuthenticatedLayout>
        my Files page! {{ $page.url }}
    </AuthenticatedLayout>
</template>
