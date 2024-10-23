<script setup>
import { ref } from 'vue'

// https://codepen.io/treknuts/pen/rNyPzmO
</script>

<template>
<div class="center">
  <h1>TubbyCreative</h1>
</div>
</template>

<style lang="scss" scoped>
*{
  padding: 0;
  margin: 0;
}
body{
  background-color: #000;
}
.center{
  position: absolute;
  text-align: center;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}
.center h1{
  color: rgba(255,0,0,0.1);
  font-size: 100px;
  text-transform: uppercase;
  font-weight: 700;
  background-size: cover;
  background-image: url(https://cdn-images-1.medium.com/max/2000/1*Jalb56N34pBIGCjQULtW3A.jpeg);
  -webkit-background-clip: text;
  animation: background-text-animation 15s linear infinite;
}
@keyframes background-text-animation {
  0%{
    background-position: left 0px top 50%;
  }
  50%{
    background-position: left 1500px top 50%;
  }
  100%{
    background-position: left 0px top 50%;
  }
}
</style>
