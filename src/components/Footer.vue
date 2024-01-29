<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="bg-gray-50 flex items-center py-2">
    <div class="cus-container w-full flex items-center justify-start">
      <div>
        <a href="/">
          <img src="../assets/logo.png" class="max-w-[10rem]" alt="Kenroz" />
        </a>
      </div>
      <p>
        © {{ currentYear }} Kenroz. All rights reserved.
      </p>
    </div>
  </footer>
</template>
