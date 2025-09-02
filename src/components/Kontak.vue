<template>
    <section id="contact" class="relative w-full bg-white text-gray-900 py-20 px-6 md:px-12 lg:px-20 overflow-hidden">
        <!-- Title -->
        <div class="text-center mb-16 relative z-10" data-aos="fade-up">
            <h2 class="text-4xl md:text-5xl font-extrabold">CONTACT US</h2>
            <div class="mt-4 w-24 h-1 bg-gradient-to-r from-red-500 to-red-700 mx-auto rounded-full"></div>
            <p class="text-gray-600 mt-6 max-w-2xl mx-auto leading-relaxed">
                Reach out to us for collaborations, inquiries, or support. We’re here to
                help you grow.
            </p>
        </div>

        <!-- Contact Cards (2 Grid Layout + Interaktif) -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 gap-8 relative z-10" data-aos="fade-up">
            <!-- Address -->
            <div
                class="group p-6 bg-white rounded-xl shadow-md border border-gray-200 hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 flex flex-col items-center text-center">
                <div
                    class="w-14 h-14 flex items-center justify-center rounded-full bg-gradient-to-r from-red-500 to-red-700 text-white text-2xl mb-4 group-hover:scale-110 group-hover:rotate-6 transition-all duration-500">
                    <i class="fas fa-map-marker-alt"></i>
                </div>
                <h3 class="font-bold text-lg mb-2">Address</h3>
                <p class="text-gray-600 leading-relaxed">
                    Jl. Banta-Bantaeng No.23 <br />
                    Makassar 90222
                </p>
            </div>

            <!-- Phone -->
            <div
                class="group p-6 bg-white rounded-xl shadow-md border border-gray-200 hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 flex flex-col items-center text-center">
                <div
                    class="w-14 h-14 flex items-center justify-center rounded-full bg-gradient-to-r from-red-500 to-red-700 text-white text-2xl mb-4 group-hover:scale-110 group-hover:-rotate-6 transition-all duration-500">
                    <i class="fas fa-phone-alt"></i>
                </div>
                <h3 class="font-bold text-lg mb-2">Phone</h3>
                <p class="text-gray-600 leading-relaxed">+62 851-1752-9191</p>
            </div>

            <!-- Email -->
            <div
                class="group p-6 bg-white rounded-xl shadow-md border border-gray-200 hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 flex flex-col items-center text-center">
                <div
                    class="w-14 h-14 flex items-center justify-center rounded-full bg-gradient-to-r from-red-500 to-red-700 text-white text-2xl mb-4 group-hover:scale-110 group-hover:rotate-12 transition-all duration-500">
                    <i class="fas fa-envelope"></i>
                </div>
                <h3 class="font-bold text-lg mb-2">Email</h3>
                <p class="text-gray-600 leading-relaxed">zeetech.id@gmail.com</p>
            </div>

            <!-- Instagram -->
            <div
                class="group p-6 bg-white rounded-xl shadow-md border border-gray-200 hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 flex flex-col items-center text-center">
                <div
                    class="w-14 h-14 flex items-center justify-center rounded-full bg-gradient-to-r from-red-500 to-red-700 text-white text-2xl mb-4 group-hover:scale-110 group-hover:-rotate-12 transition-all duration-500">
                    <i class="fab fa-instagram"></i>
                </div>
                <h3 class="font-bold text-lg mb-2">Instagram</h3>
                <a href="https://instagram.com/zeetech.id" target="_blank"
                    class="relative text-gray-600 leading-relaxed hover:text-red-600 transition-colors after:content-[''] after:block after:w-0 after:h-[2px] after:bg-red-600 after:transition-all after:duration-300 hover:after:w-full">
                    @zeetech.id
                </a>
            </div>
        </div>

        <!-- CTA Section -->
        <div class="relative z-10 mt-16 bg-gradient-to-r from-red-500 to-red-700 rounded-2xl shadow-lg p-10 text-center text-white"
            data-aos="fade-up">
            <h3 class="text-2xl font-bold mb-4 animate-pulse">Let’s Work Together 🚀</h3>
            <p class="text-gray-100 mb-6 max-w-2xl mx-auto">
                Have an idea or project in mind? Let’s bring it to life together with
                innovation and technology.
            </p>
            <a href="https://wa.me/6285117529191?text=Halo%2C%20saya%20ingin%20dibuatkan%20aplikasi"
                class="inline-block bg-white text-red-600 font-semibold px-6 py-3 rounded-lg shadow-md hover:bg-gray-100 hover:scale-110 transform transition-all duration-300">
                Get In Touch
            </a>
        </div>

        <!-- Background glow merah halus -->
        <div
            class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-red-500/5 via-transparent to-red-500/5 blur-3xl">
        </div>
    </section>
</template>
