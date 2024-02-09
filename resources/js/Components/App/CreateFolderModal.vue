<template>
    <Modal :show="props.modelValue">
        <div class="p-6">
            <h2 class="text-lg font-medium text-gray-900">
                Create new folder
            </h2>
            <div class="mt-6">
                <InputLabel for="folderName" value="folderName" />
                <TextInput type="text" id="folderName" v-model="form.name" class="mt-1 block w-full"
                    :class="form.errors.name ? ' border-red-500 focus:border-red-500 focus:ring-red-500' : ''"
                    placeholder="Folder name" @keyup.enter="createFolder" />
                <InputError :message="form.errors.name" class="mt-2" />
            </div>
            <div class="mt-6 flex justify-end">
                <SecondaryButton @click="closeModal">Cancel</SecondaryButton>
            </div>
        </div>
    </Modal>
</template>

<script setup>
import Modal from '@/Components/Modal.vue'
import InputLabel from '../InputLabel.vue';
import TextInput from '../TextInput.vue';
import InputError from '../InputError.vue';
import { useForm } from '@inertiajs/vue3';
import SecondaryButton from '../SecondaryButton.vue';

const props = defineProps({
    modelValue: {
        type: Boolean,
        default: false,
    },
});

const emit = defineEmits(['update:modelValue'])

const form = useForm({
    name: ''
})


function createFolder() {
    console.log('create folder')

}

function closeModal() {
    emit('update:modelValue');
    form.clearErrors();
    form.reset();
}

</script>
