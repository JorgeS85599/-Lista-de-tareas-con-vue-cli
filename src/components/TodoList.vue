<template>
        <ul>
            <todo-item v-for="(item,index) in todos" :key="index" :item="item" @dblclick="delToDo(index)"></todo-item>
        </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: 'todo-list',
    components: {
        TodoItem
    },
    props: ['todos'],
    methods: {
        delToDo(index) {
            this.$emit('deltodo', {position: index})
        }
    }
}
</script>

