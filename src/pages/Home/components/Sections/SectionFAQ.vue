<script setup>
import { ref } from 'vue';
import SingleFaqQuestion from '../SingleFaqQuestion.vue';

const expandedFaq = ref(null);

const toggleFaq = (faqId) => {
  expandedFaq.value = expandedFaq.value === faqId ? null : faqId;
};

const faqs = [
  {
    question: 'What is Kenroz?',
    answer: 'Kenroz is a school management service for school admins, teachers, and parents, offering features like user management, notices, tasks, holidays, and an in-app email system for communication.'
  },
  {
    question: 'Who can use Kenroz?',
    answer: 'Kenroz can be used by school admins, teachers, and parents.'
  },
  {
    question: 'Is Kenroz available for use outside of India?',
    answer: 'No. Kenroz is currently available only in India.'
  },
  {
    question: 'Does Kenroz offer different access levels for admins, teachers, and parents?',
    answer: 'Yes, we offer different access levels based on the user’s role, be it admin, teacher, or parent.'
  },
  {
    question: 'What makes Kenroz different from other school management systems?',
    answer: 'Kenroz sets itself apart through unique features and functionalities tailored for effective school management, with constant updates and new feature additions.'
  },
  {
    question: 'How does Kenroz improve school communication?',
    answer: 'Kenroz enhances school communication by having an in-app email system and allowing parents to open tickets to communicate with admins or teachers.'
  },
  {
    question: 'Are there any customization options available in Kenroz for schools?',
    answer: 'Yes, Kenroz offers customization options, and we are constantly adding more to meet the diverse needs of schools.'
  },
  {
    question: 'Does Kenroz require any special training to use?',
    answer: 'No, Kenroz is designed to be easy and simple to use, requiring no special training.'
  },
  {
    question: 'How does a school get started with Kenroz?',
    answer: 'Schools interested in Kenroz can get started by contacting us, and we will assist them with the onboarding process.'
  }
];

</script>

<template>
  <div id="faq" class="flex items-center py-5 pb-20">
    <div class="mx-auto text-start flex flex-col gap-4 max-w-[50rem]">
      <h2 class="text-6xl">Frequently Asked Questions</h2>

      <SingleFaqQuestion
        v-for="faq, index in faqs"
        :key="index"
        :isExpanded="expandedFaq === index"
        @toggle="toggleFaq(index)"
        :question="faq.question"
        :answer="faq.answer"
      />
    </div>
  </div>
</template>
