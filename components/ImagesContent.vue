<template>
  <div class="image-page">
    <div class="row text-center dog-iterate">
<!-- loop thur array and render each item -->
      <div class="col-sm" :key="image.id" v-for="image in images" >
         <ImageContent :image="image" />
      </div>
    </div>
  </div>
</template>

<script>
import ImageContent from "@/components/ImageContent.vue"

export default {
  name: "ImagesContent",
  props: {
    images: Array,
  },
  components: {
    ImageContent,
  },
};
</script>


<style scoped>
.btnstyle {
	border: red 2px solid;
  }

</style>

