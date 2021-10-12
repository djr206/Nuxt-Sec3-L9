
<template>
  <!-- example code from https://medium.com/@olaysco/dynamic-list-toggling-in-vuejs-accordion-9020a5d91497 -->
  <div id="accordion-page2">
    <Nav />  
    <Header />
    <br>
    <AccordionContent
      v-for="(item, index) in dynamicList"
      :key="index"
      :user="item"
    >
      This is {{ item.name }}, they're {{ item.age }} years old
      <br />
      <img
        class="img-fluid p-3 my-3"
        :src="item.src"
        alt=""
        width="225px"
        height="150px"
      />
      <br />
      <a href="#" target="_blank"
        >Learn more about {{ item.name }} here if desired.</a
      >
    </AccordionContent>
    <br>
    <Footer />
  </div>
</template>

<script>
export default {
  head() {
    return {
      titleTemplate: '%s - Accordion Page'
    }
  }
  ,
  data() {
    return {
      // register an empty array
      dynamicList: [],
    };
  },
  methods: {
    // prepare a list for toggling, defa to !visible
    // this data can come from outside api
    prepareDynamicList() {
      let list = [
        {
          name: "yolo",
          age: 6,
          src: require("../../assets/img/headshot1.jpg"),
        },
        {
          name: "fomo",
          age: 8,
          src: require("../../assets/img/headshot2.jpg"),
        },
        {
          name: "fido",
          age: 5,
          src: require("../../assets/img/headshot3.jpg"),
        },
      ];
      list.forEach((element) => {
        this.dynamicList.push({ ...element, visible: false });
      });
    },
  },
  async created() {
    this.prepareDynamicList();
  },
};
</script>

<style>
body {
  background-color: #dfde9f;
}
</style>
