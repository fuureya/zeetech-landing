<script setup>
const portfolioData = [
    {
        id: 1,
        title: "E-Library Ukip",
        description: "E-Library Ukip",
        image: new URL("@/assets/projects/1.jpg", import.meta.url).href,
    },
    {
        id: 2,
        title: "E-Library Ukip",
        description: "E-Library Ukip",
        image: new URL("@/assets/projects/2.jpg", import.meta.url).href,
    },
    {
        id: 3,
        title: "Company Profile SMK Persada",
        description: "Company Profile SMK Persada",
        image: new URL("@/assets/projects/3.jpg", import.meta.url).href,
    },
    {
        id: 4,
        title: "Management Keuangan Dan PPDB SMK Persada",
        description: "Management Keuangan Dan PPDB SMK Persada",
        image: new URL("@/assets/projects/4.jpg", import.meta.url).href,
    },
    {
        id: 5,
        title: "Company Profile SMK Persada",
        description: "Company Profile SMK Persada",
        image: new URL("@/assets/projects/5.jpg", import.meta.url).href,
    },
    {
        id: 6,
        title: "Company Profile SMK Persada",
        description: "Company Profile SMK Persada",
        image: new URL("@/assets/projects/6.jpg", import.meta.url).href,
    },
    {
        id: 7,
        title: "Company Profile SMK Persada",
        description: "Company Profile SMK Persada",
        image: new URL("@/assets/projects/7.jpg", import.meta.url).href,
    },
    {
        id: 8,
        title: "Arsip Digital Infolahtadam Hasanuddin Makassar",
        description: "Arsip Digital Infolahtadam Hasanuddin Makassar",
        image: new URL("@/assets/projects/8.jpg", import.meta.url).href,
    },
    {
        id: 9,
        title: "Arsip Digital Infolahtadam Hasanuddin Makassar",
        description: "Arsip Digital Infolahtadam Hasanuddin Makassar",
        image: new URL("@/assets/projects/9.jpg", import.meta.url).href,
    },
    {
        id: 10,
        title: "Aplikasi Kepuasan Alumni TSFIP UNM",
        description: "Aplikasi Kepuasan Alumni TSFIP UNM",
        image: new URL("@/assets/projects/10.jpg", import.meta.url).href,
    },
    {
        id: 11,
        title: "Aplikasi Kepuasan Alumni TSFIP UNM",
        description: "Aplikasi Kepuasan Alumni TSFIP UNM",
        image: new URL("@/assets/projects/11.jpg", import.meta.url).href,
    },
    {
        id: 12,
        title: "Aplikasi Kepuasan Alumni TSFIP UNM",
        description: "Aplikasi Kepuasan Alumni TSFIP UNM",
        image: new URL("@/assets/projects/12.jpg", import.meta.url).href,
    },
];
</script>

<template>
    <section id="portofolio"
        class="relative w-full bg-white text-gray-900 py-20 px-6 md:px-12 lg:px-20 overflow-hidden">
        <!-- Title -->
        <div class="text-center mb-16 relative z-10" data-aos="fade-up">
            <h2 class="text-4xl md:text-5xl font-extrabold">PROJECTS</h2>
            <div class="mt-4 w-24 h-1 bg-gradient-to-r from-red-500 to-red-700 mx-auto rounded-full"></div>
            <p class="text-gray-600 mt-6 max-w-2xl mx-auto leading-relaxed">
                Explore some of our latest works that showcase innovation, design, and
                technology to support business growth.
            </p>
        </div>

        <!-- Grid Projects -->
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8 relative z-10" data-aos="fade-up">
            <div v-for="item in portfolioData" :key="item.id"
                class="group relative rounded-xl overflow-hidden shadow-md border border-gray-200 bg-white hover:shadow-xl hover:scale-[1.02] transition-all duration-500 cursor-pointer">
                <!-- Image -->
                <img :src="item.image" :alt="item.title"
                    class="w-full h-56 object-cover group-hover:scale-110 transition-transform duration-700" />

                <!-- Overlay -->
                <div
                    class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500 flex flex-col justify-end p-6">
                    <h3 class="text-lg font-bold text-white mb-2">
                        {{ item.title }}
                    </h3>
                    <p class="text-sm text-gray-200">
                        {{ item.description }}
                    </p>
                </div>
            </div>
        </div>

        <!-- Background glow merah halus -->
        <div
            class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-red-500/5 via-transparent to-red-500/5 blur-3xl">
        </div>
    </section>
</template>
