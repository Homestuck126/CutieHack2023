<script setup>
import WelcomeItem from './WelcomeItem.vue'
import SlideTab from './SlideTab.vue'
</script>

<template>
  <div>
    <h3 class="header">PROJECTGRAM</h3>
    <div class="container">
      <nav class="navbar">
        <div class="dropdown">
          <button class="dropbtn">Menu</button>
          <div class="dropdown-content">
            <a href="#">Home</a>
            <a href="#">About</a>
            <a href="#">Contact</a>
            <div class="dropdown-info">
              <a href="#">Information</a>
              <div class="dropdown-info-content">
                <a href="#">FAQs</a>
                <a href="#">Terms of Use</a>
                <a href="#">Privacy Policy</a>
              </div>
            </div>
            
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    navigateTo(url) {
      window.location.href = url;
    }
  }
}
</script>
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
  left: 80%;
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
.dropdown {
  position: relative;
  left: 210%;
  display: inline-block;
}

.dropbtn {
  font-size: 22px;
  color: #fff;
  background-color: black;
  border: none;
  cursor: pointer;
}

.dropdown-content {
  display: none;
  position: absolute;
  
  z-index: 1;
  background-color: #f9f9f9;
}

.dropdown-content a {
  color: black;
  padding: 10px 15px;
  text-decoration: none;
  display: block;
}

.dropdown:hover .dropdown-content {
  display: block;
}
.dropdown-info {
    position: relative;
    display: inline-block;
  }

  .dropdown-info .dropdown-info-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    z-index: 1;
  }

  .dropdown-info:hover .dropdown-info-content {
    display: block;
  }

  .dropdown-info-content a {
    color: black;
    padding: 10px 15px;
    text-decoration: none;
    display: block;
  }
</style>
