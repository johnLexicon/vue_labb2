<template>
  <!-- Default form login -->
<form class="text-center border border-light p-5" @submit.prevent="logIn">

    <p class="h4 mb-4">Sign in</p>

    <!-- Name -->
    <input v-model="name" type="text" id="defaultLoginFormName" class="form-control mb-4" placeholder="name">

    <!-- Password -->
    <input v-model="password" type="password" id="defaultLoginFormPassword" class="form-control mb-4" placeholder="Password">

    <!-- Sign in button -->
    <button class="btn btn-info btn-block my-4" type="submit">Sign in</button>

</form>
<!-- Default form login -->
</template>

<script>
export default {
    props:['loggedIn'],
    data(){
        return {
            name:'',
            password:''
        }
    },
    methods: {
        logIn(){
            if(this.loggedIn){
                alert('You have to log out first!!!!');
                return;
            }
            const user = {name: this.name, password: this.password};
            this.$emit('logInUser', user);
        }
    }
}
</script>

<style>

</style>