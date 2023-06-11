<template>
  <div>
    <div class="img-container">
      <img ref="image" :src="src">
    </div>
    <img :src="destination" class="img-preview">
  </div>
</template>

<script>
import Cropper from "cropperjs";
export default {
  name: 'ImageCropper',
  props: {
    src: String
  },
  data(){
    return{
      cropper:{},
      destination:{},
      image: {}
    }
  },
  mounted(){
    this.image = this.$refs.image;
    this.cropper = new Cropper(this.image,{
      crop: () => {
        const canvas = this.cropper.getCroppedCanvas();
        this.destination = canvas.toDataURL("image/png");

      }
     
    });

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .img-container{
    width: 640px;
    height: 480px;
    float: left;
  }
   .img-preview{
    width: 200px;
    height: 200px;
    float: left;
    margin-left: 10px;

   }
</style>
