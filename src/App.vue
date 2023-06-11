<template>
  <div id="app">
    <ImageCropper src="/logo.png"/>
  </div>
</template>

<script>
import ImageCropper from './components/ImageCropper.vue'

export default {
  name: 'app',
  components: {
    ImageCropper
  }
}
</script>

<style></style>
