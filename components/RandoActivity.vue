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
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: left;
}

.heading {
  text-align: center;
  font-size: 2rem;
  color: #555;
  margin: 2rem auto;
}

.p-8 {
  padding: 8px;
}

.btn {
    width: 15rem;
}

</style>
