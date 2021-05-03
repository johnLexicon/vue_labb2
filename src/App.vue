<template>
  <div class="vh-100">
    <AppNavBar :loggedIn="loggedIn" :user="user" @logOutUser="logOut" />
    <div
      class="container h-100 d-flex justify-content-center align-items-center"
    >
      <AppForm :loggedIn="loggedIn" @logInUser="logIn" />
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBar";
import Form from "./components/Form";
export default {
  name: "App",
  components: {
    AppNavBar: NavBar,
    AppForm: Form,
  },
  data() {
    return {
      loggedIn: false,
      user: {},
    };
  },
  methods: {
    logIn(user) {
      this.user = user;
      this.loggedIn = true;
    },
    logOut() {
      (this.user = {}), (this.loggedIn = false);
    },
  },
};
</script>

<style>
</style>
