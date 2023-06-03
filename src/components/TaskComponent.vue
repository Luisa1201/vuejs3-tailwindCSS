<script setup>

const props = defineProps({
    name: {
        type: String,
        default: 'No tengo nombre'
    },
    index: {
        type: Number
    }
})

const emit = defineEmits([
    'emitDeleteTask'
])

const deleteTask = (index) => {
    console.log('Borrar', index)
    emit('emitDeleteTask', index)

}

</script>

<template>
    <div class="flex justify-between px-4 py-2 bg-gray-200 rounded">
        {{ props.name }}

        <span class="inline-block px-2 text-white bg-red-400 rounded hover:cursor-pointer hover:bg-red-600" @click="deleteTask(props.index)">
            X
        </span>
    </div>
    
</template>