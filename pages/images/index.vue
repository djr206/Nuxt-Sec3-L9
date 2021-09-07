<template>
<!-- this is the parent component to ImagesContent and ImageContent that
      comprise the image section of the image page, also using 
      toggleBorder.js mixin
       -->
  <div class="image-pg">
    <Nav />  
    <Header />
    <ImagesContent :images="images" />
    <Footer />
  </div>
</template>

<script> // able to remove additional import step, now handled by nuxt
// import S3L7Header from "@/assets/header/S3L7Header.vue";
// import S3L7Footer from "@/assets/footer/S3L7Footer.vue";
// import ImagesContent from "@/components/ImagesContent.vue";

export default {
//   name: "Images",
//   components: {
//     ImagesContent,
//     S3L7Header,
//     S3L7Footer,
//   },
  data() {
    return {
      images: [
                {
            picture: require("../../assets/img/headshot1.jpg"),
            alt: 'dog1', 
            name: 'dog1',
            id: 1,
        },
        { 
          picture: require("../../assets/img/headshot2.jpg"),
          alt: 'dog2', 
          name: 'dog2',
          id: 2,
        },
        { 
          picture: require("../../assets/img/headshot3.jpg"),
          alt: 'dog3', 
          name: 'dog3',
          id: 3,
        },
        { 
          picture: require("../../assets/img/headshot4.jpg"),
          alt: 'dog4', 
          name: 'dog4',
          id: 4
        },
      ],
    }
  },
  isShowing: false
}
</script>

<style lang="scss" scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap'); */

</style>
