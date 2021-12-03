<template>
    <button @click="borrarToDos">Borrar todas las tareas</button>
</template>

<script>
export default {
    name: 'delete-list',
    methods: {
        borrarToDos() {
            if (confirm('Vas a borrar todas las tareas')) {
                this.$emit('delall')
            }
        }
    }
}
</script>