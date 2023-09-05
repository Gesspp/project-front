<template>
    <div class="task" :style="{color: color}">
        <input type="checkbox" :checked="done" @input="$emit('changeTask')">
        <p :class="{done}">{{title}}</p>
        <button class="delete-task" @click="$emit('deleteTask')">-</button>
    </div>
</template>
<script>
    export default{
        data(){
            return 0;
        },
        props: {
            title: String,
            done: Boolean,
            color: String
        }
    }
</script>
<style>
    .task{
        border-radius: 10px;
        border-color: black;
        box-shadow: 0 0 5px black;
        width: 200px;
        height: 38px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    .done{
        text-decoration: line-through;
    }
    .delete-task{
        background: #ffffff;
        padding: 0.2em 0.4em;
    }
</style>