<template>
    <form @submit.prevent="onsubmit">
    
        <input type="text" v-model="text" placeholder="Search Jokes...">
        <input type="submit" value="Search">
    </form>
</template>

<script>
export default {
    name: 'DadjokesSearchJokes',

    data() {
        return {
            text:""
        };
    },

    mounted() {
        
    },

    methods: {
        onsubmit(){
            this.$emit('search-text', this.text)
            this.text = ""
        }
    },
};
</script>

<style lang="scss" scoped>

</style>