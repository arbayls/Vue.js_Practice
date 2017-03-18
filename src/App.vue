<template>
<div id="app">

    <input type="text" v-model="todo">
    <button type="button" @click="addTodo">Add To List!</button>
    <h2>Todo List</h2>
    <ul>
        <li v-for="todo in todoList">
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
            todoList: []
        }
    },
    methods: {
        addTodo: function() {
            this.todoList.push(this.todo)
        }
    }
}
</script>

<style lang="scss"></style>
