<template>
    <div class="buttons">
        <form>
            <input @click="$emit('add-todo')" type="button" value="Add" class="button">
            <input @click="$emit('remove-todo')" type="button" value="Remove" class="button">
            <input @click="$emit('clear-todo')" type="button" value="Clear" class="button">
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo"
}
</script>

<style scoped>
   form {
       display: flex;
   }
    .button {
        background-color: #4CAF50; 
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        width: 33.333333333%;
        border: 1px solid green;
        transition-duration: 0.4s;
    }
    .button:hover {
        background-color: #006400;
    }
</style>
