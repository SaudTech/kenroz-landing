<script setup>
import { inject } from '@vercel/analytics';
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Home from "./pages/Home/index.vue";

inject();
</script>

<template>
  <div class="flex flex-col min-h-screen overflow-hidden relative">
    <Header />
    <main class="flex-grow w-full">
      <Home />
    </main>
    <Footer />

    <div class="blob-one"></div>
  </div>
</template>

<style>
.underlineAnimation {
  position: relative;
  text-decoration: none;
  color: inherit;
  transition: color 300ms;
}
.underlineAnimation::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: currentColor;
  transform: scaleX(0);
  transform-origin: right;
  transition: transform 300ms;
}
.underlineAnimation:hover::before {
  transform: scaleX(1);
  transform-origin: left;
}

.blob-one {
  position: absolute;
  top: 50%;
  left: 60%;
  width: 300%;
  height: 300%;
  background-color: #c7267aa3;
  background-size: 100px;
  background-repeat: repeat;
  filter: blur(40rem);
  opacity: 0.7;
  z-index: -1;
}
</style>
