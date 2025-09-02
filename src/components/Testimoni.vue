<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import { Pagination, Autoplay } from "swiper/modules";

const testimonials = [
    {
        id: 1,
        name: "Antony Saul Rombe",
        job: "Pebisnis",
        foto: new URL("../assets/testimoni/5.png", import.meta.url).href,
        pesan:
            "Pelayanan dari Zeetech IT Solution sangat profesional, instalasi jaringan di kantor kami berjalan cepat dan rapi!",
    },
    {
        id: 2,
        name: "Lisa Tandiayu",
        job: "Pebisnis",
        foto: new URL("../assets/testimoni/7.png", import.meta.url).href,
        pesan:
            "Kami sangat puas dengan hasil web custom landing page yang dibuat oleh Zeetech—desainnya menarik dan sesuai dengan kebutuhan bisnis kami.!",
    },
    {
        id: 3,
        name: "M. Yusuf Mapparasessa",
        job: "Pebisnis",
        foto: new URL("../assets/testimoni/6.png", import.meta.url).href,
        pesan:
            "Pembuatan company profile digital oleh tim Zeetech sangat membantu memperkuat citra perusahaan kami di dunia online.",
    },
    {
        id: 4,
        name: "Agung",
        job: "Dosen ",
        foto: new URL("../assets/testimoni/8.png", import.meta.url).href,
        pesan:
            "Kami sangat terbantu dengan aplikasi kepuasan alumni yang dibuat oleh Zeetech IT Solution. Tim mereka sangat profesional dalam memahami kebutuhan kami dan menghasilkan aplikasi yang mudah digunakan, efektif, dan tepat sasaran.",
    },
    {
        id: 5,
        name: "Dedi Sudadang Infolahtadam",
        job: "Infolahtadam Hasanuddin Makassar",
        foto: new URL("../assets/testimoni/8.png", import.meta.url).href,
        pesan:
            "Kami sangat puas dengan aplikasi arsip digital yang dikembangkan oleh Zeetech IT Solution. Aplikasi ini mempermudah kami dalam mengelola arsip secara digital.",
    },
];
</script>

<template>
    <section class="bg-white py-20 px-6 md:px-12 lg:px-20">
        <!-- Title -->
        <div class="text-center mb-16" data-aos="fade-up">
            <h2 class="text-3xl md:text-4xl font-extrabold">TESTIMONIALS</h2>
            <div class="mt-4 w-24 h-1 bg-gradient-to-r from-red-500 to-red-700 mx-auto rounded-full"></div>
            <p class="text-gray-600 mt-6 max-w-2xl mx-auto">
                Discover what our clients say about working with us and how we helped
                transform their businesses.
            </p>
        </div>

        <!-- Slider -->
        <Swiper :modules="[Pagination, Autoplay]" :slides-per-view="1" :space-between="30"
            :pagination="{ clickable: true }" :breakpoints="{
                768: { slidesPerView: 2 },
                1024: { slidesPerView: 3 }
            }" :autoplay="{ delay: 4000 }" class="pb-12">
            <SwiperSlide v-for="item in testimonials" :key="item.id" class="flex justify-center">
                <div
                    class="bg-white rounded-xl shadow-md hover:shadow-xl transition-shadow duration-500 p-8 w-full max-w-sm border border-gray-200">
                    <!-- Foto -->
                    <div class="flex items-center mb-6">
                        <img :src="item.foto" :alt="item.name"
                            class="w-14 h-14 rounded-full object-cover border border-gray-200 mr-4" />
                        <div>
                            <h3 class="text-lg font-bold text-gray-800">{{ item.name }}</h3>
                            <p class="text-sm text-gray-500">{{ item.job }}</p>
                            <div class="flex mt-1 text-yellow-400">
                                <i class="fa-solid fa-star" v-for="n in 5" :key="n"></i>
                            </div>
                        </div>
                    </div>

                    <!-- Pesan -->
                    <p class="text-gray-600 text-sm leading-relaxed">
                        <i class="fa-solid fa-quote-left text-red-500 mr-2"></i>
                        {{ item.pesan }}
                    </p>
                </div>
            </SwiperSlide>
        </Swiper>
    </section>
</template>
