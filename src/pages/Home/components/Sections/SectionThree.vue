<script setup>
import { ref } from 'vue';

const email = "help@kenroz.in";
</script>

<template>
  <div id="contact" class="flex items-center h-[60vh] py-20">
    <div class="sm:w-2/4 w-full text-start flex flex-col gap-4">
      <h2 class="text-6xl">Contact Us</h2>
      <p class="text-2xl">Email us to get in contact with Kenroz team for any questions or concerns.</p>
      <a href="mailto:{{ email }}" class="text-2xl underline">
        {{ email }}
      </a>
    </div>
  </div>
</template>
