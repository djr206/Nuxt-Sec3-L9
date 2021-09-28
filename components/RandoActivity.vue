<template>
    <p v-if="$fetchState.pending">
    Fetching activity...
  </p>
  <p v-else-if="$fetchState.error">
    An error occurred :(
  </p>
  <div v-else>
      <div class="container p-8">
       <h1>Do something!</h1>
        <button type="button" class="btn btn-primary btn-lg" @click="$fetch">
        Here's an idea
        </button>
    <h3>{{ activity.activity }}</h3><br>
        <p>
       <!-- <a>{{ activity.link }}</a> -->
       <!-- <nuxt-link :to="'#'+activity.link" exact class="nav-link">{{ activity.link }}</nuxt-link> -->
       <!-- <nuxt-link :to="activity.link" exact class="nav-link">{{ activity.link }}</nuxt-link> -->
       <nuxt-link :to="activity.link" exact class="nav-link">{{ activity.link }}</nuxt-link>

    </p>
    <h3>The activity is {{ activity.type }}.</h3><br>
    <h3>The number of participants is {{ activity.participants }}.</h3><br>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      activity: null,
      type: null,
      participants: 0,
      link: ''
    }
  },
  async fetch () {
    this.activity = await fetch(
      'https://www.boredapi.com/api/activity/'
    ).then(res => res.json())
  }
}
</script>

<style scoped>
.container {
  /* min-height: 100vh; */
  /* max-width: 1200px; */
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* align-items: flex-start; */
  text-align: left;
  /* flex-wrap: wrap; */
}

.heading {
  text-align: center;
  font-size: 2rem;
  color: #555;
  margin: 2rem auto;
}

/* .title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
} */

/* .subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
} */

/* .links {
  padding-top: 15px;
} */

/* .list-item-container {
  width: 60%;
  margin: 0 auto;
  background-color: gray;
  margin-bottom: 10px;
} */

.p-8 {
  padding: 8px;
}

.btn {
    width: 15rem;
}

</style>
