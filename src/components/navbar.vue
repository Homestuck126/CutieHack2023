<script setup>
import WelcomeItem from './WelcomeItem.vue'

</script>

<template>
<h3 class="header">PROJECTGRAM</h3>
  <div class="container">
    <nav class="navbar">
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Contact</a>
    </nav>
    
  </div>
</template>

<style>
.container {
  max-width: 960px;
  margin: 0 auto;
  padding: 15x;
  
}
h3 {
  font-weight: 600;

  padding: 15px;
  top: 0;
  left: 0;
  width: 100%;
  height: 15%
}
.navbar {

  position: fixed;
  top: 0%;
  left: 81%;
font-size: 22px;
  color: #fff;
  padding: 20px;
   background-color: black;
   height: 10%;
}

.navbar a {
  color: #fff;
  text-decoration: none;
  margin-right: 15px;
}

.row {
  display: flex;
  flex-wrap: wrap;
}

.column {
  flex-basis: 33.33%;
  padding: 10px;
}

.column h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.column p {
  margin-bottom: 10px;
}
</style>
