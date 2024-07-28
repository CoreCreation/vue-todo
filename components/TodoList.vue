<script setup>
import { ref } from 'vue';
const textBox = ref('');
const items = ref([]);

function addTodo() {
    if (!!textBox.value) {
        items.value.push({
            todo: textBox.value
        });
        textBox.value = '';
    }
}
</script>

<template>
    <div class="flex gap-1 mb-1">
        <UInput v-model="textBox" class="flex-auto" size="sm" color="primary" variant="outline" placeholder="New TODO..." />
        <UButton class="flex-inital" icon="i-heroicons-plus-circle-16-solid" @click="addTodo"></UButton>
    </div>
    <ul>
        <TodoListItem v-for="(item, index) in items" :todo="item.todo" @remove="items.splice(index, 1)"></TodoListItem>
    </ul>
</template>
