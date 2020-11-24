<template>
  <div id="app" class="container">
    <AppForm/>
  </div>
</template>

<script>
import Form from './components/Form';
export default {
  name: 'App',
  components: {
    AppForm: Form
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
