<template>
    <div class="todo-item">
        <p v-bind:class="{ 'is-complete': todo.completed }">
            <input
                type="checkbox"
                v-on:change="$emit('change-complete', todo.id)"
            />
            {{ todo.title }}
        </p>
        <button class="del" v-on:click="$emit('del-todo', todo.id)">+</button>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
};
</script>

<style scoped>
.todo-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #f4f4f4;
    padding: 12px 16px;
    border-radius: 6px;
    border: 1px solid #eee;
    margin-bottom: 12px;
}
.todo-item input {
    cursor: pointer;
    margin-right: 8px;
}
.is-complete {
    text-decoration: line-through;
}
.del {
    width: 26px;
    height: 26px;
    background: #ff7979;
    color: #fff;
    border: none;
    outline: none;
    font-size: 1.2em;
    border-radius: 50%;
    transform: rotate(45deg);
    cursor: pointer;
}
.del:hover {
    background-color: #ff4f4f;
}
</style>
