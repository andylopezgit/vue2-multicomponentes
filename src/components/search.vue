<template>
    <div class="container">
        <h2>Component Search</h2>
        <section>
            <form v-on:submit.prevent="onSubmit">
                <input type="text" placeholder="Ingrese nombre" id="inputName" v-model="valSearch">
                <button @click="setSearch">Search</button>
            </form>
        </section>
    </div>
</template>
<script>
export default {
    name: "search",
    data() {
        return {
            valSearch: ''
        }
    },
    methods: {
        setSearch () {
            this.$emit('passSearch', this.valSearch)
            this.valSearch = ''
        }
    },
}
</script>
<style scoped>
    .container {
        background: rgb(64, 179, 179);
        padding: 1rem;
        margin: 1rem;
    }
    #inputName {
        margin-right: 1px;
    }
</style>