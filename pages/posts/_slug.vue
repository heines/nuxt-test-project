<template lang="pug">
  div
    h1
      |{{ doc.title }}
    div
      |{{ doc.description }}
    nuxt-content(
      :document="doc"
      )
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const doc = await $content(`posts/${params.slug}`).fetch();
    return { doc };
  },
};
</script>

<style lang="scss"></style>
