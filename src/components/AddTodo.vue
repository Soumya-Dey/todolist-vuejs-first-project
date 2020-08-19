<template>
    <div>
        <form class="add-form" v-on:submit="addTodo">
            <input
                type="text"
                name="title"
                placeholder="Add new task..."
                v-model="title"
            />
            <input type="submit" value="Submit" class="btn" />
        </form>
    </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";

export default {
    name: "AddTodo",
    data() {
        return {
            title: "",
        };
    },
    methods: {
        addTodo(event) {
            event.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false,
            };

            this.$emit("add-todo", newTodo);
            this.title = "";
        },
    },
};
</script>

<style scoped>
.add-form {
    display: flex;
    position: fixed;
    bottom: 0;
    width: 100%;
}
input[type="text"] {
    flex: 10;
    background: #ddd;
    padding: 10px 16px;
    outline: none;
    border: none;
    /* border: 1px solid #555; */
}
input[type="submit"] {
    flex: 2;
    /* border-radius: 0 6px 6px 0; */
    outline: none;
    border: none;
}
</style>
