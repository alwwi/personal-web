<script setup>
import { ref } from 'vue';
const Skills = ref([
    {
        id: 1,
        name: 'HTML & CSS',
        width: '80%',
    },
    {
        id: 2,
        name: 'React.js',
        width: '70%',
    },
    {
        id: 3,
        name: 'PHP',
        width: '50%',
    },
    {
        id: 4,
        name: 'Tailwind CSS',
        width: '70%',
    },
    {
        id: 5,
        name: 'Figma',
        width: '90%',
    },
    {
        id: 5,
        name: 'Python',
        width: '30%',
    },
])

const Experiences = ref([
    {
        id: 1,
        role: 'UI/UX Designer',
        company: 'DIGIFREN',
        date: 'Sep 2024 - Des 2024'
    },
    {
        id: 2,
        role: 'Asisten Dosen Matakuliah Forensika Digital',
        company: 'Jurusan Informatika UII',
        date: 'Jan 2024 - Jun 2024'
    },
])

const Organizations = ref([
    {
        id: 1,
        role: 'Ketua Steering Committee',
        event: 'Pekan Olahraga dan Seni Mahasiswa Informatika 2022',
        date: 'Jul 2022 - Nov 2022'
    },
    {
        id: 2,
        role: 'Ketua Organizing Committee',
        event: 'Ospek Jurusan Informatika 2023',
        date: 'Oct 2022 - Des 2023'
    },
])
</script>

<template>
    <section class="text-white mt-36" id="skills">
        <div class="absolute right-0 w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
                <h2 class="text-4xl font-bold text-white text-left mb-4">My
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in Skills" :key="skill.id">
                    <div class="flex items-end justify-between" data-aos="fade-right">
                        <h4 class="font-semibold uppercase text-white">
                            {{ skill.name }}
                        </h4>
                        <h3 class="text-2xl font-bold text-white">{{ skill.width }}</h3>
                    </div>
                    <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                        <div class="h-1 rounded-full bg-primary " :style="`width :${skill.width}`"></div>
                    </div>
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-8">My Experience
                </h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="experience in Experiences" :key="experience.id"
                        class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border-[#1f1641]">
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3
                                class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                {{ experience.role }}
                            </h3>
                            <p class="text-white"> {{ experience.company }}</p>
                            <p class="text-white">{{ experience.date }}</p>
                        </div>
                    </div>

                    <div v-for="organization in Organizations" :key="organization.id"
                        class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border-[#1f1641]">
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/ios-filled/100/ffffff/diploma.png" alt="lawyer">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3
                                class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                {{ organization.role }}
                            </h3>
                            <p class="text-white"> {{ organization.event }}</p>
                            <p class="text-white">{{ organization.date }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>