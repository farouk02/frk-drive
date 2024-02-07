<script setup>
import TextInput from '@/Components/TextInput.vue';
import { useForm } from '@inertiajs/vue3';

const form = useForm({
    search: ''
})

</script>


<template>
    <form class="w-[600px] h-[80px] flex items-center" action="">
        <TextInput type="text" id="searchField" name="search" class="block w-full mr-2" v-model="form.search"
            autocomplete="true" placeholder="Type to find files" />
    </form>
</template>
