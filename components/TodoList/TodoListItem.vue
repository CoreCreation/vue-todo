
<script setup>
const props = defineProps(['todo']);
</script>

<template>
    <div class="flex gap-1 mb-1">
        <li class="flex-auto">{{ props.todo }}</li>
        <UButton color="red" class="flex-inital" icon="i-heroicons-x-circle-16-solid" @click="$emit('remove')"></UButton>
    </div>
</template>
