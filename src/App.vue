<template>
<div id="app">

    <input type="text" v-model="todo">
    <button type="button" @click="addTodo">Add To List!</button>
    <h2>Todo List</h2>
    <ul>
        <li v-for="todo in todoList">
            {{todo}}
            <button type="button" @click="completeTodo(todo)">Complete</button>
            <button type="button" @click="removeTodo(todo)">Remove</button>
        </li>
    </ul>
    <h2>Completed Todos</h2>
    <ul>
      <li v-for="todo in completedTodos">
        {{todo}}
      </li>
    </ul>
</div>
</template>

<script>
export default {
    name: 'app',
    data() {
        return {
            msg: 'Welcome to Your Vue.js App',
            todo: '',
            todoList: [],
            completedTodos: []
        }
    },
    methods: {
        addTodo: function() {
            this.todoList.push(this.todo)
            this.todo = ''
        },
        completeTodo: function(listicle) {
            this.completedTodos.push(listicle)
            this.todoList.splice(this.todoList.indexOf(listicle), 1)
        },
        removeTodo: function(listicle) {
            this.todoList.splice(this.todoList.indexOf(listicle), 1)
        }
    }
}
</script>

<style lang="scss"></style>
