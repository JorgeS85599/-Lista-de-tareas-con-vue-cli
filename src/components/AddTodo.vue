<template>
    <form @submit.prevent="addToDo">
        <input type="text" v-model="nuevoToDo">
        <button type="submit">AÃ±adir</button>
    </form>
</template>

<script>
export default {
    name: 'add.todo',
    data() {
        return {
             nuevoToDo: ''
        }
    },
    methods: {
        addToDo() {
            if (this.nuevoToDo) {
                this.$emit('addtodo', {
                    descrip: this.nuevoToDo,
                    done: false
                })
                this.nuevoToDo = ''
            }
        },
    }
}
</script>