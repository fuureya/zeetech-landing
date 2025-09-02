<script setup>
import { ref } from "vue";

const faqs = [
    {
        id: 1,
        question: "What IT services does Zeetech offer?",
        answer:
            "Zeetech offers a range of IT services, including landing page creation, company profiles, custom web apps, network configuration, and web design tailored to your business needs.",
    },
    {
        id: 2,
        question: "How can I order a landing page service from Zeetech?",
        answer:
            "You can order a landing page service by contacting our team through our website or email. We will discuss your specific needs and provide a suitable quote.",
    },
    {
        id: 3,
        question: "Can Zeetech create custom web apps for my business?",
        answer:
            "Yes, Zeetech specializes in building custom web apps that are tailored to your business processes, from internal applications to more complex platforms.",
    },
    {
        id: 4,
        question: "Does Zeetech provide web design services for businesses?",
        answer:
            "Absolutely! We offer professional web design services to create websites that are not only attractive but also functional, aligned with your company's identity and goals.",
    },
    {
        id: 5,
        question: "Does Zeetech help with network configuration for businesses?",
        answer:
            "Yes, we provide network configuration services to ensure your IT infrastructure runs smoothly, securely, and can support your business growth.",
    },
    {
        id: 6,
        question: "How long does it take to complete a website project with Zeetech?",
        answer:
            "The time needed for a project depends on its complexity. For simpler websites like landing pages, it usually takes 1-2 weeks, while more complex projects may take longer.",
    },
];

const activeIndex = ref(null);

const toggleFaq = (index) => {
    activeIndex.value = activeIndex.value === index ? null : index;
};
</script>

<template>
    <section class="py-20 px-6 md:px-12 lg:px-20 bg-gray-50 text-gray-900">
        <!-- Title -->
        <div class="text-center mb-12" data-aos="fade-up">
            <h2 class="text-4xl md:text-5xl font-extrabold">Frequently Asked Questions</h2>
            <p class="text-gray-600 mt-4 max-w-2xl mx-auto leading-relaxed">
                Have questions? We've compiled the most common ones to help you get the information you need.
            </p>
        </div>

        <!-- FAQ List -->
        <div class="max-w-3xl mx-auto space-y-4">
            <div v-for="(faq, index) in faqs" :key="faq.id" class="p-[1px] rounded-xl transition-all duration-300"
                :class="activeIndex === index ? 'bg-gradient-to-r from-red-500 to-red-600' : 'bg-transparent'">
                <div
                    class="border rounded-xl bg-white shadow-md hover:shadow-lg transition-all duration-300 overflow-hidden">
                    <!-- Question -->
                    <button @click="toggleFaq(index)"
                        class="w-full flex justify-between items-center p-5 text-left text-lg font-semibold">
                        <span>{{ faq.question }}</span>
                        <span
                            class="ml-3 flex items-center justify-center w-8 h-8 rounded-full bg-gray-100 text-gray-600 transition-all duration-300"
                            :class="activeIndex === index ? 'bg-gradient-to-r from-red-500 to-red-600 text-white rotate-180' : ''">
                            <svg v-if="activeIndex !== index" xmlns="http://www.w3.org/2000/svg" class="h-5 w-5"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M12 4v16m8-8H4" />
                            </svg>
                            <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none"
                                viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4" />
                            </svg>
                        </span>
                    </button>

                    <!-- Answer -->
                    <transition name="faq" mode="out-in">
                        <div v-show="activeIndex === index" class="px-5 pb-5 text-gray-600 leading-relaxed">
                            {{ faq.answer }}
                        </div>
                    </transition>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.faq-enter-active,
.faq-leave-active {
    transition: all 0.3s ease;
}

.faq-enter-from,
.faq-leave-to {
    opacity: 0;
    max-height: 0;
}

.faq-enter-to,
.faq-leave-from {
    opacity: 1;
    max-height: 500px;
}
</style>
