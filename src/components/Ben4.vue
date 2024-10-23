<script setup>
import { ref } from 'vue'
</script>

export default {  
 makeNewPosition($container) {
    // Get viewport dimensions (remove the dimension of the div)
    var h = $container.height() - 50;
    var w = $container.width() - 50;

    var nh = Math.floor(Math.random() * h);
    var nw = Math.floor(Math.random() * w);

    return [nh, nw];
  },
  animateDiv($target) {
    var newq = makeNewPosition($target.parent());
    var oldq = $target.offset();
    var speed = calcSpeed([oldq.top, oldq.left], newq);

    $target.animate({
        top: newq[0],
        left: newq[1]
    }, speed, function() {
        animateDiv($target);
    });
  },
  calcSpeed(prev, next) {
    var x = Math.abs(prev[1] - next[1]);
    var y = Math.abs(prev[0] - next[0]);

    var greatest = x > y ? x : y;
    var speedModifier = 0.1;
    var speed = Math.ceil(greatest / speedModifier);
    return speed;
  },
  mounted() {
    console.log("MOUNTED")
    animateDiv($('.a'));
    animateDiv($('.b'));
    animateDiv($('.c'));
  }
}

<template>
  <div id="container">
  <div class='a'></div>
      <div class='b'></div>
      <div class='c'></div>
  </div>
</template>



<style lang="scss" scoped>
div#container {height:500px;width:500px;}

div.a {
width: 50px;
height:50px;
 background-color:red;
position:fixed;
    
}
div.b {
width: 50px;
height:50px;
 background-color:blue;
position:fixed;
    
}
div.c {
width: 50px;
height:50px;
 background-color:green;
position:fixed;
    
}

</style>
