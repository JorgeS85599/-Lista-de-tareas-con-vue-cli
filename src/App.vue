<template>
    <div id="app">
        <h1>{{ title }}</h1>
        <todo-list v-if="toDos.length" :todos="toDos" @deltodo="delToDo"></todo-list>
        <p v-else>No hay tareas que mostrar</p>
        <add-todo @addtodo="anyadirToDo"></add-todo>
        <delete-list @delall="deleteList"></delete-list>
    </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import AddTodo from './components/AddTodo.vue'
import DeleteList from './components/DeleteList.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    AddTodo,
    DeleteList
  },
  data() {
        return {
            title: 'Cosas ha hacer',
            toDos: [
                {
                    id: 1,
                    descrip: 'Aprender Vue',
                    done: false
                },
                {
                    id: 2,
                    descrip: 'Dominar Vue',
                    done: false
                }
            ]
        }
    },
    methods: {
        delToDo(index) {
            this.toDos.splice(index.position, 1)
        },
        deleteList() {
            this.toDos = []
        },
        anyadirToDo(nuevoToDo) {
            this.toDos.push(nuevoToDo)
        }
    },
}
</script>
