<template>
  <header class="header">
    <div class="topnav">

      <!-- Centered link -->
      <div class="topnav-centered">
        <a href="#home" class="active">Home</a>
      </div>

      <!-- Left-aligned links (default) -->
      <a href="#news">News</a>
      <a href="#contact">Contact</a>

      <!-- Right-aligned links -->
      <div class="topnav-right">
        <a href="#search">Search</a>
        <a href="#about">About</a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
.header {
  /* margin-top: 30px; */
}

.topnav {
  position: relative;
  background-color: #333;
  overflow: hidden;
}

/* Style the links inside the navigation bar */
.topnav a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

/* Change the color of links on hover */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

/* Add a color to the active/current link */
.topnav a.active {
  background-color: #04aa6d;
  color: white;
}

/* Centered section inside the top navigation */
.topnav-centered a {
  float: none;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Right-aligned section inside the top navigation */
.topnav-right {
  float: right;
}
</style>