<script setup>
import WelcomeItem from './WelcomeItem.vue'

</script>

<template>
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
  padding: 20px;
}

.navbar {

  position: fixed;
  top: 0;
  left: 0;
font-size: 20px;
  color: #fff;
  padding: 20px;
}

.navbar a {
  color: #fff;
  text-decoration: none;
  margin-right: 20px;
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
