<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark padding">
    <NuxtLink class="navbar-brand" to="/">
      Landing Page
    </NuxtLink>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon" />
    </button>
    <div id="navbarSupportedContent" class="collapse navbar-collapse ml-auto">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active">
          <NuxtLink to="/activity" class="nav-link">
            Activity <span class="sr-only">(current)</span>
          </NuxtLink>
        </li>

        <li class="nav-item active">
          <NuxtLink to="/images" class="nav-link">
            Images <span class="sr-only">(current)</span>
          </NuxtLink>
        </li>
        <li class="nav-item active">
          <NuxtLink to="/grid" class="nav-link">
            Grid <span class="sr-only">(current)</span>
          </NuxtLink>
        </li>
        <li class="nav-item active">
          <NuxtLink to="/accordion" class="nav-link">
            Accordion <span class="sr-only">(current)</span>
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
    .padding {
        padding: 1.5rem;
        background-color: black;
        margin-bottom: 5rem;
    }

</style>
