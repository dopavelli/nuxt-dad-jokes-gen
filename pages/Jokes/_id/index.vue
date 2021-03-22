<template>
  <div>
    <nuxt-link to="/jokes">Back to jokes...</nuxt-link>
    <hr />
    <br />
    <h4>
      {{ joke }}
    </h4>
    <br />
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {}
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
    } catch (error) {
      console.log(error);
    }
  },
  head() {
    return {
      title: this.$route.params.id,
      meta: [
        {
          hid: "description",
          name: this.joke,
          content: this.joke
        }
      ]
    };
  }
};
</script>

<style></style>
