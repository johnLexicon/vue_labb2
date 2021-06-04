<template>
  <!-- Just an image -->
  <nav class="navbar navbar-dark fixed-top">
    <a class="navbar-brand" href="#">
      <img src="@/assets/img/lexicon.jpg" height="30" alt="Lexicon logo" />
    </a>

    <div v-if="loggedIn === false">
      <span class="navbar-text text-muted"> Please Log In </span>
    </div>
    <div v-else>
      <span class="navbar-text text-muted">
        Logged in as: {{ user.name }}
      </span>
      <button @click="logOut" class="btn btn-danger btn-sm" type="button">
        Log out
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  props: ["loggedIn", "user"],
  methods: {
    logOut() {
      this.$emit("logOutUser");
    },
  },
};
</script>

<style scoped>
div span {
  font-weight: 400;
  margin-right: 1rem;
}
</style>