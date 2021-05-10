<template>
  <div class="min-h-screen bg-blue-50 py-4 px-3">
    <div>
      <p class="text-center font-bold text-4xl m-3">One Line Hacks</p>
      <p class="text-center font-light text-2xl m-3">
        A collection of random utilities that I find myself Googling too often.
      </p>
      <div v-for="hack in hacks" :key="hack.title">
        <Hack :hack="hack" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const hacks = await $content("hacks")
      .only(["title", "tags", "description", "url", "body", "slug"])
      .sortBy("createdAt", "asc")
      .fetch();

    return {
      hacks,
    };
  },
};
</script>

<style></style>
