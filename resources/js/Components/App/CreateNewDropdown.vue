<script setup>
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue'
import ResponsiveNavLink from "@/Components/ResponsiveNavLink.vue"
import CreateFolderModal from './CreateFolderModal.vue';
import { ref } from 'vue';

const createFolderModal = ref(false);

function showCreateNewFolderModal() {
    createFolderModal.value = true
}
</script>

<template>
    <Menu as="div" class="relative block text-left">
        <MenuButton
            class="flex w-full justify-center gap-x-1.5 rounded-md bg-white px-3 py-2 text-sm font-semibold to-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50">
            Create new
        </MenuButton>

        <transition enter-active-class="transition duration-100 ease-out" enter-from-class="transform scale-95 opacity-0"
            enter-to-class="transform scale-100 opacity-100" leave-active-class="transition duration-75 ease-in"
            leave-from-class="transform scale-100 opacity-100" leave-to-class="transform scale-95 opacity-0">
            <MenuItems
                class="absolute right-0 mt-2 w-full origin-top-right divide-y divide-gray-100 rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                <div class="px-1 py-1">
                    <MenuItem v-slot="{ active }">
                    <a href="#" @click.prevent="showCreateNewFolderModal"
                        :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">
                        New folder
                    </a>
                    </MenuItem>
                    <MenuItem v-slot="{ active }">
                    <ResponsiveNavLink href="#" method="post" as="button"
                        :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">
                        Upload folder
                    </ResponsiveNavLink>
                    </MenuItem>
                    <MenuItem v-slot="{ active }">
                    <ResponsiveNavLink href="#" method="post" as="button"
                        :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">
                        Upload file
                    </ResponsiveNavLink>
                    </MenuItem>
                </div>
            </MenuItems>
        </transition>
    </Menu>
    <CreateFolderModal v-model="createFolderModal" />
</template>
