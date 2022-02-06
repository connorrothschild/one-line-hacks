<template>
<div>
  <div class="min-h-screen bg-blue-50 p-3">
    <div>
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
    </div>
  </div>
      <footer class="bg-blue-200 p-6 w-full text-center font-light">
        <a href="https://www.connorrothschild.com/"
          >Made by Connor Rothschild</a
        >
      </footer>
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
  head: {
    title: "One Line Hacks | Connor Rothschild",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        hid: "description",
        name: "description",
        content:
          "A collection of random utilities that I find myself Googling too often.",
      },
      { name: "twitter:site", content: "@CL_Rothschild" },
      { name: "twitter:card", content: "summary_large_image" },
      {
        hid: "og:image",
        property: "og:image",
        content: "https://connorrothschild.github.io/one-line-hacks/social.png",
      },
      {
        hid: "twitter:url",
        name: "twitter:url",
        content: "https://connorrothschild.github.io/one-line-hacks/",
      },
      {
        hid: "twitter:title",
        name: "twitter:title",
        content: "One Line Hacks | Connor Rothschild",
      },
      {
        hid: "twitter:description",
        name: "twitter:description",
        content:
          "A collection of random utilities that I find myself Googling too often.",
      },
      {
        hid: "twitter:image",
        name: "twitter:image",
        content: "https://connorrothschild.github.io/one-line-hacks/social.png",
      },
    ],
    link: [{ rel: "icon", type: "image/png", href: "https://connorrothschild.github.io/one-line-hacks/favicon.png" }],
  },
};
</script>

<style></style>
