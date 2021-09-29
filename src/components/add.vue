<template>
    <div class="container">
        <form v-on:submit.prevent="onSubmit">
            <input  type="text" placeholder="add your task" v-model="task">
            <button @click="addTask">Add</button>
        </form>
    </div>
</template>
<script>
export default {
    name: "add",
    data() {
        return {
            task: '',
            tasks: []
        }
    },
    methods: {
        addTask () {
            this.tasks.push(this.task)
            this.$emit("emitAdd", this.tasks)
            this.task = ''
        }
    },
}
</script>
<style scoped>
    .container {
        background-color: darkcyan;
        margin: 1rem;
        padding: 1rem;
    }
</style>