<script setup>
import { ref } from 'vue';
import ColorPicker from './ColorPicker.vue';

const isUploading = ref(false)
const hasFile = ref(false)
const uploadFile = () => {
      isUploading.value= true;
      // simulate file upload with 5-second delay
      setTimeout(() => {
        // once the 5-second delay is complete, set isUploading back to false
        isUploading.value = false;
        hasFile.value = true;
      }, 1300);
}

</script>

 <!-- template  --> 
<template>
  
  <form>
    <!-- Grid --> 
    <article v-if="!isUploading && !hasFile">
      <ColorPicker />
      <hr>
      <label for="upload">
        Upload a photo
        <input type="file" id="upload" name="file" @change="uploadFile" required> 
      </label>
    </article>

  <!-- Grid --> 
  <div v-if="isUploading">
      <h3>
        Generating avatars, please wait ...
      </h3>
      <progress indeterminate="true"></progress>

  </div>
  
  <article v-if="hasFile" class="grid">
      <img src="../assets/output.jpeg" width="600">
  </article>

</form>

</template>