<script setup>
import { ref } from "vue";

const expandedDiv = ref(0);

const divs = [
  {
    title: "For Admins",
    description:
      "For Admins, Kenroz provides a easy-to-use interface to manage their school. It allows them to manage anything from users to classes to subjects to exams and more. It also provides a way to communicate with parents and teachers.",
    features: [
      "In-app email system",
      "Easy & one-time setup",
      "Easy to use interface",
    ],
  },
  {
    title: "For Teacher",
    description:
      "Kenroz allows teachers to manage their classes, students, student work, and more all in one place.",
    features: [
      "In-app email system",
      "Manage tasks, assignments, and exams",
      "Online grading system",
    ],
  },
  {
    title: "For Parents",
    description:
      "Kenroz is fast, easy-to-use, and reliable for parents to monitor their childrens. It is a web-based application that can be accessed from any device. Soon to be available on Android and iOS.",
    features: [
      "In-app email system",
      "Monitor childrens progress and daily work",
      "Simple, straightforward interface",
    ],
  },
];
</script>

<template>
  <div id="services" class="flex flex-col sm:flex-row w-full gap-1 bg-gray-200 p-4 mx-auto mt-10 sm:h-[30rem]">
    <div
      v-for="(box, index) in divs"
      :key="index"
      class="flex flex-col h-full min-w-20 text-start text-white rounded-md p-4 transition-all duration-500"
      :class="[
        expandedDiv === index ? 'sm:w-[70%] bg-[#121316]' : 'sm:w-[15%] bg-[#1E1E1E]',
      ]"
      @mouseover="expandedDiv = index"
    >
      <div class="flex-grow">
        <h3 class="font-bold text-3xl">
          {{ box.title }}
        </h3>
        <p v-if="expandedDiv === index" class="w-2/4 mt-3">
          {{ box.description }}
        </p>
      </div>
      <ul v-if="box.features && expandedDiv === index" class="text">
        <li v-for="fe in box.features" :key="fe">
          ✅ {{ fe }}
        </li>
      </ul>
      <p v-if="expandedDiv !== index" :class="[expandedDiv === index ? 'w-2/4 mt-3' : 'truncate']">
          {{ box.description }}
        </p>
    </div>
  </div>
  <!-- <div class="h-full w-full pt-10 mt-20">
    <div
      class="h-[30rem] w-[40rem] bg-gray-800 text-white rounded-md text-start p-3"
    >
      <h4 class="text-2xl font-semibold tracking-wider">
        For School officials
      </h4>
    </div>
  </div> -->
</template>
