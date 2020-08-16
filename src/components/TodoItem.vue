<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed">
            {{index + 1}}.
            {{todo.title}}
        </span>
        <button class="rm" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
    </li>
</template>

<script>
    export default {
        props: {
            todo: {
                type: Object,
                required: true
            },
            index: Number
        }
    }
</script>

<style scoped>
    li {
        border: 1px solid #cccccc;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }

    .rm {
        background-color: tomato;
        color: #fff;
        width: 1.5rem;
        height: 1.5rem;
        border-radius: 50%;
        cursor: pointer;
        border: none;
    }

    .done {
        text-decoration: line-through;
    }
</style>