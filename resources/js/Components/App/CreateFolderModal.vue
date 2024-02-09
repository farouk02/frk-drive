<template>
    <Modal :show="props.modelValue">
        farouk
    </Modal>
</template>

<script setup>
import Modal from '@/Components/Modal.vue'

const props = defineProps({
    modelValue: {
        type: Boolean,
        default: false,
    },
});

console.log(props.modelValue)
</script>
