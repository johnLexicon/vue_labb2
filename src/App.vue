<template>
  <div id="app" class="container mt-4">
    <AppNavBar :loggedIn="loggedIn" :user="user" @logOutUser="logOut" />
    <AppForm :loggedIn="loggedIn" @logInUser="logIn" />
  </div>
</template>

<script>
import NavBar from './components/NavBar';
import Form from './components/Form';
export default {
  name: 'App',
  components: {
    AppNavBar: NavBar,
    AppForm: Form
  },
  data(){
    return {
      loggedIn: false,
      user: {},
    }
  },
  methods:{
    logIn(user){
      this.user = user;
      this.loggedIn = true;
    },
    logOut(){
      this.user = {},
      this.loggedIn = false;
    }
  }
}
</script>

<style>
  *{
    margin:0;
    padding:0;
    box-sizing: border-box;
  }
</style>
