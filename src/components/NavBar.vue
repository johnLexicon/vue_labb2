<template>
  <!-- Just an image -->
  <nav class="navbar navbar-dark primary-color">
    <a class="navbar-brand" href="#">
      <img
        src="https://mdbootstrap.com/img/logo/mdb-transparent.png"
        height="30"
        alt="mdb logo"
      />
    </a>

    <div v-if="loggedIn === false">
        <span class="navbar-text white-text">
          Please Log In
        </span>
    </div>
    <div v-else>
        <span class="navbar-text white-text">
            {{ user.name }}
        </span>
        <button @click="logOut" class="btn btn-outline-white" type="button">Log out</button>
    </div>
  </nav>
</template>

<script>
export default {
    props: ['loggedIn', 'user'],
    methods: {
        logOut(){
            this.$emit('logOutUser');
        }
    }
};
</script>

<style>
</style>