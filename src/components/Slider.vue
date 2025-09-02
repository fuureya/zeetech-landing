<script setup>
// Array logo asli (10 file)
const logos = Array.from(
    { length: 10 },
    (_, i) => new URL(`../assets/client/${i + 1}.png`, import.meta.url).href
);
</script>

<template>
    <div class="relative w-full max-w-6xl mx-auto py-8">
        <!-- Scrollable container -->
        <div class="flex gap-4 overflow-x-auto scrollbar-hide snap-x snap-mandatory px-2">
            <div v-for="(logo, idx) in logos" :key="idx"
                class="flex-none min-w-[200px] sm:min-w-[150px] flex justify-center items-center snap-start">
                <!-- Kotak 1:1 -->
                <div
                    class="w-full aspect-square bg-white rounded-xl shadow-md flex items-center justify-center hover:shadow-xl hover:scale-105 transition-all duration-300">
                    <img :src="logo" alt="logo" class="w-3/4 h-3/4 object-contain" />
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Hide scrollbar (Chrome, Safari, Edge) */
.scrollbar-hide::-webkit-scrollbar {
    display: none;
}

/* Hide scrollbar (Firefox) */
.scrollbar-hide {
    scrollbar-width: none;
}
</style>
