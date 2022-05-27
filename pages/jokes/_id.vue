<template>
  <div>
    <nuxt-link class="center" to="/jokes">>Back To Jokes</nuxt-link>
    <br /><br />
    <hr />
    <hr />
    <hr />
    <h2>{{ joke }}</h2>
    <hr />
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
export default {
  name: "DadjokesId",

  data() {
    return {
      joke: "",
    };
  },

  head() {
    return {
      title: this.joke,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes",
        },
      ],
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    let id = this.$route.params.id;
    await this.$axios.$get(`/j/${id}`, config).then((res) => {
      this.joke = res.joke;
      console.log(res.joke);
    });
    console.log(id);
  },

  methods: {},
};
</script>

<style scoped>
.center {
  text-align: center;
}
</style>
