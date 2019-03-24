<template>
  <div>
    <img :src="imageUrl" alt="image">
  </div>
</template>
<script>
import { ipcRenderer } from "electron";
export default {
  data() {
    return {
      imageUrl: ""
    };
  },
  created() {
    ipcRenderer.on("image", (event, arg) => {
      this.imageUrl = arg;
    });
  }
};
</script>
<style scoped>
img {
  max-width: 100%;
}
</style>


