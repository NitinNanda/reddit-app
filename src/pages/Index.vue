<template>
  <q-page>
    <q-spinner
    v-if = "loading"
    color="primary"
    size="3em" />
    <q-list v-else bordered>
      <q-item
        clickable
        v-ripple
        v-for="post in posts"
        :key ="post.data.id">
        <q-item-section avatar>
          <q-avatar size="60px">
            <img :src="post.data.thumbnail" />
          </q-avatar>
        </q-item-section>
        <q-item-section>{{post.data.title}}</q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  created () {
    this.$axios
      .get('https://www.reddit.com/r/aww.json?raw_json=1')
      .then(response => {
        this.loading = false
        this.posts = response.data.data.children
      })
      .catch(err => {
        this.loading = false
        console.log(err)
      })
  },
  data () {
    return {
      loading: true,
      posts: []
    }
  }
}
</script>
