<template>
  <div>
    <Nav />
    <Header />
    <Home msg="Landing Page Content" />
    <Footer/>
  </div>
</template>

<script>
export default {
    head() {
    return {
      titleTemplate: '%s - Landing Page'
    }
  }
  ,
}
</script>
