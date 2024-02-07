<script setup>
import { Link } from '@inertiajs/vue3'
import ApplicationLogo from '@/Components/ApplicationLogo.vue'
import NavLink from '@/Components/NavLink.vue'
import CreateNewDropdown from '@/Components/App/CreateNewDropdown.vue'
</script>

<template>
    <nav class=" min-w-[200px]">
        <div class="h-[80px] px-3 flex items-center gap-3">
            <Link :href="route('myFiles')">
            <ApplicationLogo class="inline-block mr-3 h-9 w-auto fill-current text-gray-800" />
            FRK Drive
            </Link>
        </div>
        <div class="px-3">
            <CreateNewDropdown />
            <div class="py-3">
                <NavLink :href="route('myFiles')" :active="$page.url === 'my-files'">My Files</NavLink>
                <NavLink href="/dashboard">Shared with me</NavLink>
                <NavLink href="/dashboard">Shared by me</NavLink>
                <NavLink href="/dashboard">Starred Files</NavLink>
                <NavLink href="/dashboard">Trash</NavLink>
            </div>
        </div>
    </nav>
</template>
