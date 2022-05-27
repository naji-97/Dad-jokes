<template>
    <div >
        <nuxt-link :to="/jokes/ + id">
        <div class="joke">
        <span>{{joke}}</span>
        </div>
        </nuxt-link>
    </div>
</template>

<script>
export default {
    name: 'Joke',
    props:['joke', "id"],

    data() {
        return {
            
        };
    },

    mounted() {
        
    },

    methods: {
        
    },
};
</script>

<style scoped>
.joke{
    padding: 1rem;
    border: 1px dotted #CCC;
    margin: 1rem 0;
    cursor:pointer
}

</style>