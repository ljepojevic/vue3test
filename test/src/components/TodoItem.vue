<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{ todo.title }}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #eee;
        padding: 10px;
        border-bottom: 1px solid #ccc;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: red;
        color: #fff;
        border: none;
        border-radius: 50px;
        padding: 0 0px;
        height: 20px;
        width: 20px;
        float: right;

    }
</style>
