<script setup>
const services = [
    {
        icon: "fa-solid fa-globe",
        title: "Company Profile",
        desc: "We create company profiles that reflect your brand identity with professional and elegant designs, ensuring your company stands out."
    },
    {
        icon: "fa-solid fa-window-maximize",
        title: "Landing Page",
        desc: "We create effective landing pages to grab attention and support your business growth with designs that maximize conversions."
    },
    {
        icon: "fa-solid fa-screwdriver-wrench",
        title: "Custom Web App",
        desc: "We provide custom web applications tailored to your business needs, from simple applications to complex digital solutions."
    },
    {
        icon: "fa-solid fa-network-wired",
        title: "Network Configuration",
        desc: "Our network configuration services ensure secure and efficient connectivity to support your business performance and reliability."
    }
];
</script>

<template>
    <section
        class="relative w-full bg-gradient-to-br from-gray-900 via-black to-gray-800 text-white py-20 px-6 md:px-12 lg:px-20 overflow-hidden">

        <!-- Title -->
        <div class="text-center mb-16 relative z-10" data-aos="fade-up">
            <h2 class="text-4xl md:text-5xl font-extrabold">SERVICES</h2>
            <div class="mt-4 w-24 h-1 bg-gradient-to-r from-red-500 to-red-700 mx-auto rounded-full"></div>
            <p class="text-gray-400 mt-6 max-w-2xl mx-auto leading-relaxed">
                Building digital excellence with custom websites, landing pages, and seamless network solutions.
            </p>
        </div>

        <!-- Services Grid -->
        <div class="grid md:grid-cols-2 gap-8 relative z-10">
            <div v-for="(service, idx) in services" :key="idx"
                class="group bg-gray-800/70 border border-gray-700 p-8 rounded-xl shadow-lg flex items-start gap-6 transition-all duration-500 hover:bg-gradient-to-tr hover:from-red-600 hover:to-red-400 hover:scale-[1.02] cursor-pointer">

                <!-- Icon -->
                <div class="text-red-500 group-hover:text-white text-4xl transition-all duration-300">
                    <i :class="service.icon"></i>
                </div>

                <!-- Text -->
                <div>
                    <h3 class="font-bold text-xl mb-2 group-hover:text-white transition-all">
                        {{ service.title }}
                    </h3>
                    <p class="text-gray-400 group-hover:text-gray-100 text-sm leading-relaxed">
                        {{ service.desc }}
                    </p>
                </div>
            </div>
        </div>

        <!-- Background glow -->
        <div
            class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-red-500/10 via-transparent to-red-500/10 blur-3xl">
        </div>
    </section>
</template>
