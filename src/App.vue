<script setup>
import 'bootstrap/dist/css/bootstrap.min.css';

</script>
<template>
  <div id="app">
 <ul>
    
<li> <router-link to="/">Home</router-link> </li>
 <li> <router-link to="/login">Login</router-link> </li> 
 <router-view></router-view> 
 </ul>
  </div>
</template>

<style scoped>
ul {
   
    margin: 0 auto;
    padding: 0;
    list-style-type: none;
    margin-bottom: 10px;
}

li {
    display: inline;
    padding: 5px;
    margin: 30px;
    
}

</style>

