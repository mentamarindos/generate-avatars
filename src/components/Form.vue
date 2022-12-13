<script setup>
import { ref } from 'vue';

const file = ref();

</script>

 <!-- template  -->
<template>

<h1>Avatar generator using Python</h1>

<form>
  <!-- Grid -->
  <div class="grid">
    <label for="upload">
      Upload a photo
      <input type="file" id="upload" name="file" required> 
    </label>
  </div>
  <!-- Grid -->
  <div class="grid">
    <h3>Result</h3>
  </div>
</form>

</template>