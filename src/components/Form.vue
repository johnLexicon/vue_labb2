<template>
  <!-- Default form login -->
  <form class="text-center p-5 w-75 shadow" @submit.prevent="logIn">
    <p class="h4 mb-4">Sign in</p>

    <!-- Name -->
    <input
      v-model="user.name"
      type="text"
      id="defaultLoginFormName"
      class="form-control mb-4"
      placeholder="name"
      required
    />

    <!-- Password -->
    <input
      v-model="user.password"
      type="password"
      id="defaultLoginFormPassword"
      class="form-control mb-4"
      placeholder="Password"
      required
    />

    <!-- Sign in button -->
    <button
      :disabled="loggedIn"
      class="btn btn-danger btn-block my-4"
      type="submit"
    >
      Sign in
    </button>
  </form>
  <!-- Default form login -->
</template>

<script>
export default {
  props: ["loggedIn"],
  data() {
    return {
      user: {
        name: "",
        password: "",
      },
    };
  },
  methods: {
    logIn() {
      if (this.loggedIn) {
        alert("You have to log out first!!!!");
        return;
      }
      this.$emit("logInUser", { ...this.user }); // Copying object with the spread operator.
      //   this.$emit("logInUser", Object.assign({}, this.user)); //Copying object with Object.assign
      this.user = { name: "", password: "" };
    },
  },
};
</script>

<style>
</style>