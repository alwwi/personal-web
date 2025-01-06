<script setup>
import { ref } from 'vue';
const Education = ref([
    {
        id: 1,
        school: 'Universitas Islam Indonesia',
        program: 'Informatics',
        year: '2021 - Present',
    },
]);

const Certificates = ref([
    {
        id: 1,
        Title: 'Belajar Dasar Pemrograman Web',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/NVP7Q1WG4ZR0',
    },
    {
        id: 2,
        Title: 'Belajar Dasar Pemrograman JavaScript',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/GRX5ODOGKP0M',
    },
    {
        id: 3,
        Title: 'Belajar Membuat Front-End Web untuk Pemula',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/MEPJNYN94X3V',
    },
    {
        id: 4,
        Title: 'Belajar Back-End Pemula dengan JavaScript',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/KEXLY8340ZG2',
    },
    {
        id: 5,
        Title: 'Cloud Practitioner Essentials (Belajar Dasar AWS Cloud)',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/KEXLY8Q20ZG2',
    },
    {
        id: 6,
        Title: 'Belajar Dasar AI',
        from: 'Dicoding',
        link: 'https://www.dicoding.com/certificates/98XW58Q3JPM3',
    },
]);
</script>

<template>
    <section class="text-white mt-56" id="about">
        <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start">
            <div class="h-24 w-64 bg-gradient-to-br from-primary via-secondary blur-2xl to-[#570cac] opacity-20"></div>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 z-1">
            <div data-aos="flip-right" class="h-full mt-4 md:mt-0">
                <h2 class="text-4xl font-bold text-white text-left mb-8 ">My Education</h2>
                <div class="space-y-8 py-8">
                    <div v-for="element in Education" :key="element.id"
                    class="flex items-center md:w-[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] h-32 px-4"
                    >
                    <div class="w-1/4">
                        <img src="https://img.icons8.com/ios-glyphs/60/ffffff/graduation-cap--v1.png" alt="graduation-cap--v1">
                    </div>
                    <div class="w-3/4 pl-4 ">
                        <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                            {{ element.school }}
                        </h3>
                        <p class="text-white">{{ element.program }}</p>
                        <p class="text-white">{{ element.year }}</p>
                    </div>
                    </div>
                </div>

                <h2 class="text-4xl font-bold text-white text-left mb-8 mt-12">My Certificates</h2>
                <div class="space-y-8 py-8" v-for="element in Certificates" :key="element.id">
                    <a :href="element.link" 
                    class="flex items-center md:w-[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] h-32 px-4"
                    >
                        
                            <div class="w-1/4">
                                <img src="https://img.icons8.com/ios-filled/80/ffffff/diploma.png" alt="diploma">
                            </div>
                            <div class="w-3/4 pl-4 ">
                                <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                                    {{ element.Title }}
                                </h3>
                                <p class="text-white">{{ element.from }}</p>
                            </div>
                        
                        </a>
                </div>
            </div>
            

            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white md:text-center text-left mb-4 ">More
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">About</span>
                    Me
                </h2>
                <p class="text-base lg:text-lg mt-8 py-8 text-justify">
                    Mahasiswa informatika yang memiliki antusiasme di bidang pengembangan perangkat lunak, 
                    sedang mencari posisi magang untuk memanfaatkan keterampilan pemrograman serta menambah pengalaman. 
                    Berpengalaman dalam mengembangkan aplikasi web yang dapat diskalakan dan memiliki sedikit pengalaman dalam manajemen basis data dan pengembangan API.
                </p>
                <!-- <div class="grid grid-cols-3 gap-4 max-w-lg pt-8">
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3 ">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">+200</h3>
                        <p class="text-sm sm:text-base text-gray-300">Happy client</p>
                    </div>
                </div> -->
            </div>
        </div>
    </section>
</template>