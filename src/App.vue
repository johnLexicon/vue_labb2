<template>
  <div id="app" class="container">
    <AppNavBar :loggedIn="loggedIn"/>
    <AppForm/>
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
      loggedIn: false
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
