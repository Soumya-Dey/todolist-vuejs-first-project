<template>
    <div class="todo-cont">
        <p>My Todos</p>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem
                v-bind:todo="todo"
                v-on:change-complete="$emit('change-complete', todo.id)"
                v-on:del-todo="$emit('del-todo', todo.id)"
            />
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
    name: "Todos",
    components: { TodoItem },
    props: ["todos"],
};
</script>

<style scoped>
.todo-cont p {
    font-weight: bold;
    margin-bottom: 12px;
    color: #42b983;
    padding-left: 6px;
}
</style>
