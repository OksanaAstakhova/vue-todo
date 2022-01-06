<template>
    <li>
        <span v-bind:class="{through:todo.completed}">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
            <span>{{ index + 1 }}</span>
            {{ todo.title }}
        </span>
        <button class="btn-close" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
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
};
</script>

<style scoped>
    li {
        max-width: 680px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        text-align: center;
        padding: 5px;
        color: #f8eff8;
        font-size: 17px;
    }
    input, span {
        margin-right: 8px;
    }
    .btn-close {
        margin: 0 10px;
        border: none;
        outline: none;
        background-color: #204647;
        border-radius: 50%;
        color: #fff;
        font-size: 16px;
        cursor: pointer;
    }
    .through {
        text-decoration: line-through;
    }
</style>
