<script setup>
import { ref, onMounted } from "vue";
import bgImage from "@/assets/bg.jpg";

const offsetY = ref(0);
const handleScroll = () => {
    offsetY.value = window.scrollY * 0.5;
};

onMounted(() => {
    window.addEventListener("scroll", handleScroll);
});

// Typewriter effect
const fullText = "Better Digital Experience With Zeetech";
const displayedText = ref("");
let index = 0;

const typeWriter = () => {
    if (index < fullText.length) {
        displayedText.value += fullText[index];
        index++;
        setTimeout(typeWriter, 100); // kecepatan mengetik (ms)
    }
};

onMounted(() => {
    typeWriter();
});
</script>

<template>
    <section id="home"
        class="relative w-full h-screen flex items-center justify-center overflow-hidden bg-center bg-no-repeat bg-cover"
        :style="{
            backgroundImage: `url(${bgImage})`,
            backgroundPositionY: offsetY + 'px'
        }">
        <!-- Overlay -->
        <div class="absolute inset-0 bg-black/50"></div>

        <!-- Konten -->
        <div class="relative z-10 w-full max-w-3xl px-4 md:px-6 text-center">
            <h1 class="text-3xl sm:text-4xl md:text-6xl font-bold text-white mb-6 whitespace-pre-wrap break-words">
                {{ displayedText }}<span class="blinking-cursor">|</span>
            </h1>
            <p class="text-white text-base sm:text-lg md:text-xl mb-8">
                We are a team of skilled designers creating landing pages, company profiles, custom websites, and
                providing network configuration solutions to elevate your business online.
            </p>
            <a href="https://wa.me/6285117529191?text=Halo%2C%20saya%20ingin%20dibuatkan%20aplikasi"
                class="inline-block bg-gradient-to-r from-red-500 to-red-700 text-white font-semibold px-6 py-3 rounded-lg shadow-lg hover:scale-105 transform transition-all duration-300">
                Get Started
            </a>

        </div>
    </section>
</template>

<style scoped>
/* Fade-in animasi */
@keyframes fadeIn {
    0% {
        opacity: 0;
        transform: translateY(20px);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fadeIn {
    animation: fadeIn 1s ease forwards;
}

/* Blinking cursor */
.blinking-cursor {
    display: inline-block;
    width: 1ch;
    animation: blink 0.7s step-end infinite;
}

@keyframes blink {

    0%,
    50% {
        opacity: 1;
    }

    50.01%,
    100% {
        opacity: 0;
    }
}
</style>
