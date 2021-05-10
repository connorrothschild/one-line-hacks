<template>
  <div class="bg-white shadow-lg m-6 p-6 rounded max-w-2xl mx-auto">
    <p class="text-lg font-bold">
      {{ hack.title }}
      <span
        class="text-sm bg-blue-900 text-white p-1 mx-1 shadow-sm rounded-sm decoration-clone"
        v-for="(tag, index) in hack.tags"
        :key="index"
        >{{ tag }}</span
      >
    </p>
    <div class="py-3 border-b-2 border-gray-200">
      <p class="font-light" v-html="hack.description"></p>
    </div>
    <div class="my-3">
      <nuxt-content :document="hack" />
    </div>
    <a
      class="block text-right uppercase tracking-wider text-red-700 hover:text-black text-sm"
      target="_blank"
      rel="noopener noreferrer"
      :href="hack.url"
      >More info</a
    >
  </div>
</template>

<script>
export default {
  props: {
    hack: {
      type: Object,
      required: true,
    },
  },
  mounted() {
    console.log(this.hack);
  },
};
</script>

<style>
.nuxt-content p {
  margin-top: 0.7rem;
}

.nuxt-content h1 {
  font-size: 1.2rem;
  font-weight: bold;
  margin-top: 1rem;
}

/* purgecss ignore */
code:not(.nuxt-content-highlight > pre > code) {
  background: #831843;
  color: white;
  padding: 0.25rem;
  border-radius: 2px;
}

pre[class*="language-"]:after {
  display: block;
  height: 1rem;
  line-height: 1rem;
  font-size: 0.8rem;
  font-weight: 200;
  text-align: right;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}

.language-js::after,
.language-javascript::after {
  content: "Javascript";
}

.language-shell::after,
.language-bash::after {
  content: "Command Line";
}

.language-css::after {
  content: "CSS";
}
</style>
