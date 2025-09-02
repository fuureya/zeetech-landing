<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import { Pagination } from "swiper/modules";

const modules = [Pagination];

const portfolioData = [
    {
        name: "Muh. Alif Anhar",
        role: "Programmer",
        img: new URL("@/assets/team/1.png", import.meta.url).href,
    },
    {
        name: "Fajar Chakra",
        role: "Mobile & Web Developer",
        img: new URL("@/assets/team/4.png", import.meta.url).href,
    },
    {
        name: "Gilang Ryan",
        role: "UI/UX Specialist",
        img: new URL("@/assets/team/3.png", import.meta.url).href,
    },
    {
        name: "Muhammad Amin Hidayat",
        role: "Web Developer",
        img: new URL("@/assets/team/5.png", import.meta.url).href,
    },
    {
        name: "Agil Jibrin",
        role: "Web & Network Specialist",
        img: new URL("@/assets/team/2.png", import.meta.url).href,
    },
];
</script>

<template>
    <section id="team" class="relative w-full bg-white text-gray-900 py-20 px-6 md:px-12 lg:px-20 overflow-hidden">
        <!-- Title -->
        <div class="text-center mb-16 relative z-10" data-aos="fade-up">
            <h2 class="text-4xl md:text-5xl font-extrabold">TEAMS</h2>
            <div class="mt-4 w-24 h-1 bg-gradient-to-r from-red-500 to-red-700 mx-auto rounded-full"></div>
            <p class="text-gray-600 mt-6 max-w-2xl mx-auto leading-relaxed">
                A talented team, a shared vision — together we build solutions that move businesses forward.
            </p>
        </div>

        <!-- Swiper Slider -->
        <Swiper :modules="modules" :slides-per-view="1" :space-between="20" :breakpoints="{
            640: { slidesPerView: 1, spaceBetween: 20 },
            768: { slidesPerView: 2, spaceBetween: 24 },
            1024: { slidesPerView: 3, spaceBetween: 32 }
        }" :pagination="{ clickable: true }" class="relative z-10">
            <SwiperSlide v-for="(item, index) in portfolioData" :key="index">
                <div
                    class="group relative rounded-xl overflow-hidden shadow-md border border-gray-200 bg-white hover:shadow-xl hover:scale-[1.02] transition-all duration-500 cursor-pointer">
                    <!-- Image -->
                    <img :src="item.img" :alt="item.name"
                        class="w-full h-80 object-cover group-hover:scale-110 transition-transform duration-700" />

                    <!-- Overlay -->
                    <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent 
                               opacity-100 md:opacity-0 md:group-hover:opacity-100 
                               transition-opacity duration-500 flex flex-col justify-end p-6">
                        <h3 class="text-lg font-bold text-white mb-2">
                            {{ item.name }}
                        </h3>
                        <p class="text-sm text-gray-200">
                            {{ item.role }}
                        </p>
                    </div>
                </div>
            </SwiperSlide>
        </Swiper>

        <!-- Background glow merah halus -->
        <div
            class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-red-500/5 via-transparent to-red-500/5 blur-3xl">
        </div>
    </section>
</template>
