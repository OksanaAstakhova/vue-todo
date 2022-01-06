<template>
    <form v-on:submit.prevent="onSubmit">
        <input type="text" v-model="title" />
        <button type="submit">Add Do</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            title: ''
        };
    },
    methods: {
        onSubmit() {
            console.log(this.title);
            if (this.title.trim()) {  // trim убирает отступы справа и слева
                let newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }
                this.$emit('add-todo', newTodo); // создали событие 
                this.title = '';
            } 
        }
    }
};
</script>


<style scoped>
    form {
        display: flex;
        justify-content: center;
    }
    input {
        margin-right: 20px;
        padding: 5px;
        border: 1px solid #ddeeff;
        border-radius: 5px;
        width: 250px;
        margin-bottom: 30px;
        margin-top: 20px;
    }
    button {
        background-color: #316966;
        color: #fff;
        border: 1px solid #fff;
        padding: 0 19px;
        text-transform: uppercase;
        border-radius: 5px;
        cursor: pointer;
    }
</style>