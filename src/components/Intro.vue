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
    <section id="about"
        class="relative w-full bg-gradient-to-br from-gray-900 via-black to-gray-800 text-white py-16 px-6 md:px-12 lg:px-20 overflow-hidden">
        <!-- Left Content -->
        <div class="grid md:grid-cols-2 gap-12 items-center relative z-10">
            <!-- Text -->
            <div data-aos="fade-right">
                <h2 class="text-4xl md:text-5xl font-extrabold mb-6">
                    Zeetech
                </h2>
                <p class="text-gray-300 mb-8 leading-relaxed">
                    We are a digital service provider that focuses on creating landing
                    pages, custom websites, company profiles, and network configurations.
                    We help your business appear professional, grow in the digital world,
                    and build a reliable and efficient network infrastructure.
                </p>
                <a href="https://wa.me/6285117529191?text=Halo%2C%20saya%20ingin%20dibuatkan%20aplikasi"
                    class="px-6 py-3 rounded-full border-2 border-red-500 text-red-500 font-semibold hover:bg-red-500 hover:text-white transition-all duration-300 shadow-md hover:shadow-red-500/40">
                    Get Started <i class="fa-solid fa-arrow-right ml-2"></i>
                </a>
            </div>

            <!-- Services -->
            <div class="grid sm:grid-cols-2 gap-8" data-aos="fade-left">
                <div v-for="(service, idx) in services" :key="idx"
                    class="group bg-gray-800/70 p-6 rounded-xl shadow-lg hover:bg-gradient-to-tr hover:from-red-600 hover:to-red-400 transition-all duration-500 hover:scale-105 cursor-pointer">
                    <div class="text-red-500 group-hover:text-white text-4xl mb-4 transition-all duration-300">
                        <i :class="service.icon"></i>
                    </div>
                    <h3 class="font-bold text-lg mb-2 group-hover:text-white transition-all">
                        {{ service.title }}
                    </h3>
                    <p class="text-gray-400 group-hover:text-gray-100 text-sm leading-relaxed">
                        {{ service.desc }}
                    </p>
                </div>
            </div>
        </div>

        <!-- Background glow effect -->
        <div
            class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-red-500/10 via-transparent to-red-500/10 blur-3xl">
        </div>
    </section>
</template>
