<template>
    <div>
        <form @submit.prevent="onSubmit">
            <input type="text" v-model="text" placeholder="Search....">
            <input type="button" value="search">
        </form>
    </div>
</template>

<script>
export default {
    name: 'SearchJokes',
    data() {
        return { text: {} }
    },
    methods: {
        onSubmit() {
            this.$emit('searchText', this.text);
            this.text = '';
        }
    }
}
</script>
