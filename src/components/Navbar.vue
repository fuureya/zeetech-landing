<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import { useRoute } from "vue-router";

const isOpen = ref(false);
const isScrolled = ref(false);
const route = useRoute(); // 🔥 cek route aktif

const toggleMenu = () => {
    isOpen.value = !isOpen.value;
};

const handleScroll = () => {
    isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
    window.addEventListener("scroll", handleScroll);
});
onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
});

const menuItems = [
    { name: "Home", path: "/" },
    { name: "About", path: "/about" },
    { name: "Service", path: "/service" },
    { name: "Portofolio", path: "/portofolio" },
    { name: "Team", path: "/team" },
    { name: "Contact", path: "/contact" },
];
</script>

<template>
    <header :class="[
        'fixed w-full z-50 transition-all duration-500',
        isScrolled
            ? 'bg-gradient-to-r from-gray-800 via-gray-900 to-black backdrop-blur-md shadow-lg text-white'
            : ' text-white'
    ]">
        <div class="max-w-7xl mx-auto flex items-center justify-between px-4 py-3 md:py-4">
            <!-- Logo -->
            <div class="text-2xl font-bold">
                <router-link to="/">
                    <img src="@/assets/zee.png" class="w-20" alt="zeetech-logo" />
                </router-link>
            </div>

            <!-- Menu Desktop -->
            <nav class="hidden md:flex space-x-6">
                <router-link v-for="item in menuItems" :key="item.name" :to="item.path" :class="[
                    'transition-all duration-300 transform hover:-translate-y-1 hover:scale-105',
                    route.path === item.path
                        ? 'text-red-500 font-semibold'
                        : 'hover:text-red-500'
                ]">
                    {{ item.name }}
                </router-link>
            </nav>

            <!-- Hamburger Mobile -->
            <div class="md:hidden">
                <button @click="toggleMenu" class="focus:outline-none">
                    <svg v-if="!isOpen" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none"
                        viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M4 6h16M4 12h16M4 18h16" />
                    </svg>
                    <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
                        stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
            </div>
        </div>

        <!-- Mobile Menu -->
        <transition name="slide-fade">
            <div v-if="isOpen"
                class="md:hidden fixed top-0 right-0 w-3/4 max-w-xs h-full bg-gradient-to-b from-gray-800 to-gray-900/95 backdrop-blur-md text-white shadow-lg z-40 flex flex-col p-6">
                <div class="flex justify-end mb-6">
                    <button @click="isOpen = false" class="text-white hover:text-red-500 focus:outline-none">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
                            stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M6 18L18 6M6 6l12 12" />
                        </svg>
                    </button>
                </div>

                <nav class="flex flex-col space-y-4">
                    <router-link v-for="(item, idx) in menuItems" :key="item.name" :to="item.path" :class="[
                        'text-lg font-semibold transition-all duration-300 transform hover:scale-105',
                        route.path === item.path
                            ? 'text-red-500'
                            : 'hover:text-red-500'
                    ]" @click="isOpen = false" :style="{ transitionDelay: `${idx * 100}ms` }">
                        {{ item.name }}
                    </router-link>
                </nav>
            </div>
        </transition>
    </header>
</template>

<style scoped>
header {
    top: 0;
    left: 0;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: all 0.3s ease;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    opacity: 0;
    transform: translateX(100%);
}

.slide-fade-enter-to,
.slide-fade-leave-from {
    opacity: 1;
    transform: translateX(0);
}
</style>
