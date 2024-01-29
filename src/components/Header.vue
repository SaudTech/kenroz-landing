<script setup>
const links = [
  {
    name: "Services",
    url: "/services",
  },
  {
    name: "About us",
    url: "/about",
  },
  {
    name: "Contact",
    url: "/contact",
  },
];
</script>

<template>
  <nav class="cus-container w-full flex justify-between items-center">
    <div class="sm:mx-0 mx-auto">
      <a class="logo vue text-4xl font-normal" href="/">
        <img
          class="max-w-[16rem]"
          src="http://143.244.133.88/_nuxt/img/kenroz-logo-dark.4566577.png"
        />
      </a>
    </div>
    <ul class="list-none gap-10 sm:flex hidden">
      <a
        class="text-inherit font-normal underlineAnimation"
        v-for="link in links"
        :key="link.name"
        :href="link.url"
        >{{ link.name }}</a
      >
    </ul>
  </nav>
</template>

<style scoped>

.logo {
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #81277e6e);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #81277e6e);
}
</style>
