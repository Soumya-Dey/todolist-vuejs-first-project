<template>
    <div id="app">
        <div class="container">
            <Todos
                v-bind:todos="todos"
                v-on:change-complete="changeComplete"
                v-on:del-todo="deleteTodoItem"
            />
        </div>
        <AddTodo v-on:add-todo="addTodoItem" />
    </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";

export default {
    name: "Home",
    components: { Todos, AddTodo },
    data() {
        return {
            todos: [],
        };
    },
    methods: {
        changeComplete(id) {
            this.todos.forEach((todo) => {
                if (todo.id === id) todo.completed = !todo.completed;
            });
            localStorage.setItem("todos", JSON.stringify(this.todos));
        },
        deleteTodoItem(id) {
            this.todos = this.todos.filter((todo) => todo.id !== id);
            localStorage.setItem("todos", JSON.stringify(this.todos));
        },
        addTodoItem(newTodoItem) {
            this.todos.push(newTodoItem);
            localStorage.setItem("todos", JSON.stringify(this.todos));
        },
    },
    created() {
        this.todos = JSON.parse(localStorage.getItem("todos")) || [];
    },
};
</script>
