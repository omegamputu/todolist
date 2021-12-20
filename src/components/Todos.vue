<template>
    <section class="todoapp">
        <header class="header">
            <h1>Todos</h1>
            <input type="text" class="new-todo" placeholder="Ajouter une tâche" v-model="newTodo" @keyup.enter="addTodo">
        </header>
        <div class="main">
            <ul class="todo-list">
                <li class="todo" v-for="todo in todos" :key="todo.id" :class="{completed: todo.completed}">
                    <div class="view">
                        <input type="checkbox" v-model="todo.completed" class="toggle">
                        <label>{{ todo.name }}</label>
                    </div>
                </li>
            </ul>
        </div>
    </section>
</template>

<script>

export default {
    data () {
        return {
            todos: [
                {
                    id: 0,
                    name: 'Tâche de test',
                    completed: false
                }
            ],
            newTodo: '',
        }
    },
    methods: {
        addTodo () {
            this.todos.push({
                name: this.newTodo,
                completed: false
            })
            this.newTodo = ''
        }
    }
}
</script>

<style src="./todos.css"></style>
