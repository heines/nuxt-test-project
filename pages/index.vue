<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline"
          >Welcome to the Vuetify + Nuxt.js template
        </v-card-title>
        <v-card-text>
          <div v-for="(post, index) in posts" :key="index">
            <nuxt-link :to="post.path">
              {{ post.title }}
            </nuxt-link>
          </div>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/inspire"> Continue </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
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
