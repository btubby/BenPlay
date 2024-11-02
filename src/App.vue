<template>

  <div class="loading-section" >  
    <img id="title-image" :src="titleImage" />
</div>

  <Bubble />
  <Y/>
      
</template>

<script setup>
import Ben from './components/Ben.vue'
import Ben2 from './components/Ben2.vue'
import Ben3 from './components/Ben3.vue'
import Ben4 from './components/Ben4.vue'
import Bubble from './components/Bubble.vue'
import Ben6 from './components/Ben6.vue'
import X from './components/x.vue'
import Y from './components/y.vue'
import titleImage from './assets/loading.gif'
import { onMounted, ref } from 'vue'

// const tOpacity = ref(1);
const tHeight = ref('30%');
const tDisplay = ref('flex');
const iDisplay = ref('none');

setTimeout(function() { tDisplay.value = "none"}, 1500);

for (let i = 30; i < 80; i++) {
  setTimeout(function() { 
    var h = i 
     iDisplay.value = "flex";
    tHeight.value = `${h}%`
  }, i*20);
}
</script>

<style scoped>

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

#title-image {
  /* opacity: v-bind('tOpacity'); */
  height: v-bind('tHeight');
  display: v-bind('iDisplay');
}
.loading-section {
  display: v-bind('tDisplay');
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #e1dccf;
    background: white;
    justify-content: center;
    align-items: center;
    z-index: 1000;
    overflow: hidden;
}

</style>
