<template lang="pug">
  v-row(
    justify="center"
    align="center"
    )
    v-col(
      cols="12"
      sm="8"
      md="6"
    )
      v-card
        v-card-title(
          class="headline"
          )
          |Welcome to the Vuetify + Nuxt.js template
        v-card-text
          div(
            v-for="(post, index) in posts"
            :key="index"
            )
            nuxt-link(
              :to="post.path"
              )
              |{{ post.title }}
        v-card-actions
          v-spacer
          v-btn(
            color="primary"
            nuxt
            to="/inspire"
            )
            |Continue
</template>
<script>
export default {
  async fetch() {
    this.posts = await this.$content('posts').fetch();
  },
  data() {
    return {
      posts: [],
    };
  },
};
</script>
