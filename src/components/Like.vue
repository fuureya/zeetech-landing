<template>
    <section class="py-16 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8" ref="statsSection">
            <div v-for="(stat, index) in stats" :key="index"
                class="bg-white rounded-2xl shadow-lg p-8 text-center transform transition duration-300 hover:-translate-y-2 hover:shadow-2xl">
                <!-- Icon Circle -->
                <div
                    class="mx-auto flex items-center justify-center w-16 h-16 rounded-full bg-gradient-to-r from-red-500 to-red-700 text-white text-2xl shadow-md mb-6">
                    <i :class="stat.icon"></i>
                </div>

                <!-- Number dengan animasi -->
                <h2 class="text-4xl font-extrabold text-gray-800 mb-2">
                    {{ stat.current }}
                </h2>

                <!-- Label -->
                <p class="text-gray-500 font-medium">{{ stat.label }}</p>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

const statsSection = ref(null);
const stats = ref([
    { number: 232, current: 0, label: "Happy Clients", icon: "fa-solid fa-face-smile" },
    { number: 521, current: 0, label: "Projects", icon: "fa-solid fa-list-check" },
    { number: 24, current: 0, label: "Hours Of Support", icon: "fa-solid fa-headset" },
    { number: 4, current: 0, label: "Hard Workers", icon: "fa-solid fa-users" },
]);

// Fungsi animasi counter
const animateCount = (stat, duration = 1500) => {
    const start = 0;
    const end = stat.number;
    const range = end - start;
    const increment = end > start ? 1 : -1;
    const stepTime = Math.abs(Math.floor(duration / range));

    let current = start;
    const timer = setInterval(() => {
        current += increment;
        stat.current = current;
        if (current === end) clearInterval(timer);
    }, stepTime);
};

onMounted(() => {
    const observer = new IntersectionObserver(
        (entries) => {
            if (entries[0].isIntersecting) {
                stats.value.forEach((stat) => animateCount(stat));
                observer.disconnect();
            }
        },
        { threshold: 0.3 }
    );

    if (statsSection.value) {
        observer.observe(statsSection.value);
    }
});
</script>
