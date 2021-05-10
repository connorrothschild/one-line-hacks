<template>
  <article>
    <nuxt-content :document="hack" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const hack = await $content("hacks", params.slug).fetch();

    return { hack };
  },
};
</script>
