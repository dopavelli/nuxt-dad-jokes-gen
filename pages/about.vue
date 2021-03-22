<template>
  <div>
    <p>This is an app that displays cheesy, corny and cringy dad jokes.</p>
    <br />
    <small>version: 1.0.0</small>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About DadJokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>

<style></style>
