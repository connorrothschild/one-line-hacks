<template>
  <div class="min-h-screen bg-blue-50">
    <div class='px-3'>
      <div class="pt-6">
        <p class="text-center font-bold text-4xl">One Line Hacks</p>
        <p class="text-center font-light text-2xl m-3">
          A collection of random utilities that I find myself Googling too
          often.
        </p>
      </div>
      <div v-for="hack in hacks" :key="hack.title">
        <Hack :hack="hack" />
      </div>
      <footer class="bg-blue-200 p-6 mt-12 w-full text-center font-light">
        <a class='underline' href="https://www.connorrothschild.com/"
          >Made by Connor Rothschild</a
        >
      </footer>
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
