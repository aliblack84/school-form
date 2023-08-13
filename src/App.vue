<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <div class="div">
  <main>
<br>    
    
    <RouterView />

  </main>
</div>
</template>
<style scoped>
@import url('https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css');

@font-face {
  font-family: "B Homa";
  src: url(B_Homa.ttf);
}

@tailwind base;
@tailwind components;
@tailwind utilities;

.div{


  background-image: url('./back.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  
  /* Additional suggestions */
  width: 100%; /* Set a width for the div */
  height: 125vh; /* Set a height using viewport height units */
  position: relative; /* Ensure proper positioning */
  overflow: hidden; /* Prevent content overflow affecting image */

}


</style>
