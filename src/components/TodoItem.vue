<template>
    <div class="todo-item">
        <p>{{todo.title + (todo.number +1)}}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"]
    }
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #cccccc dotted;
    }
</style>
