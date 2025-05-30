<script setup>
import { ref, computed } from 'vue';
const project = ref([
    {
        id: 1,
        category: 'web development',
        img: '/e-farm.jpg',
        title: 'Project e-farm',
        desc: 'Merupakan proyek pribadi yang dibuat  untuk meningkatkanskill. proyek ini merupakan website layanan dan penjualan produk peternakan.',
        technologies: ['React.js', 'Tailwind', 'Bootstrap', 'Firebase'],
        projectUrl: 'https://github.com',
        Url: 'https://e-farm-jade.vercel.app/',
    },
    {
        id: 2,
        category: 'figma',
        img: '/lumiere.jpg',
        title: 'Project Redesign',
        desc: 'Tugas yang dikerjakan selama magang di DIGIFREN untuk melakukan perubahan desain pada website Lumiere.',
        technologies: ['Figma'],
        projectUrl: 'https://www.figma.com/design/gEUfvXTgseIWtrruXFqmzn/web-huruf-timbul?node-id=35-665&t=vbFKdGjmat6sy4rI-1',
        Url: 'https://www.figma.com/design/gEUfvXTgseIWtrruXFqmzn/web-huruf-timbul?node-id=35-665&t=vbFKdGjmat6sy4rI-1',
    },
    {
        id: 3,
        category: 'figma',
        img: '/jagoanaluminium.jpg',
        title: 'Project Redesign',
        desc: 'Tugas yang dikerjakan selama magang di DIGIFREN untuk melakukan perubahan desain pada website Jagoan Aluminium.',
        technologies: ['Figma'],
        projectUrl: 'https://www.figma.com/design/rd8Cc4T3u4lQnxJ7MhHzmq/Desain-Jagoan-Aluminum?node-id=0-1&t=vbFKdGjmat6sy4rI-1',
        Url: 'https://www.figma.com/design/rd8Cc4T3u4lQnxJ7MhHzmq/Desain-Jagoan-Aluminum?node-id=0-1&t=vbFKdGjmat6sy4rI-1',
    },
    {
        id: 4,
        category: 'web development',
        img: '/quiz-web-app.png',
        title: 'Project Quiz Web App',
        desc: 'Membuat portofolio project menggunakan open API kuis dari Trivia.',
        technologies: ['React.js', 'Tailwind', 'Vite'],
        projectUrl: 'https://github.com/alwwi/quiz-web-app.git',
        Url: 'https://quiz-web-app-phi-azure.vercel.app/',
    }

])

const selectedCategory = ref('all');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'all') {
        return project.value;
    }
    return project.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
});
const shouldShowIcon = (category) => {
    return selectedCategory.value === 'all' && project.category === 'web development'|| category === 'web development';
};


</script>

<template>
    <section class="text-white mt-36" id="gallery">
        <div class="px-4 xl:pl-16">
            <div class="mb-6 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white">My Latest Project</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['all', 'web development', 'figma']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                        :style="{ backgroundImage: 'url(' + project.img + ')', backgroundSize: 'cover' }">
                        <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                        hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500 
                        ">
                            <a v-if="selectedCategory === 'all' && project.category === 'web development' || selectedCategory === 'web development'" class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#adb7be] hover:border-white group/link"
                                :href="project.Url"> 
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                    viewBox="0 0 30 30" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                    data-slot="icon"
                                    class="h-10 w-10 text-[#adb8be] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 cursor-pointer group-hover/link:text-white">
                                    <path stroke-linecap="round" stroke-linejoin="round"
                                        d="M 15 5 C 6.081703 5 0.32098813 14.21118 0.21679688 14.378906 A 1 1 0 0 0 0 15 A 1 1 0 0 0 0.16210938 15.544922 A 1 1 0 0 0 0.16601562 15.550781 C 0.18320928 15.586261 5.0188313 25 15 25 C 24.938822 25 29.767326 15.678741 29.826172 15.564453 A 1 1 0 0 0 29.837891 15.544922 A 1 1 0 0 0 30 15 A 1 1 0 0 0 29.785156 14.380859 A 1 1 0 0 0 29.783203 14.378906 C 29.679012 14.21118 23.918297 5 15 5 z M 15 8 C 18.866 8 22 11.134 22 15 C 22 18.866 18.866 22 15 22 C 11.134 22 8 18.866 8 15 C 8 11.134 11.134 8 15 8 z M 15 12 A 3 3 0 0 0 12 15 A 3 3 0 0 0 15 18 A 3 3 0 0 0 18 15 A 3 3 0 0 0 15 12 z">
                                    </path>
                                </svg>
                            </a>
                            <a v-if="selectedCategory === 'all' && project.category === 'figma' || selectedCategory === 'figma'" class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#adb7be] hover:border-white group/link"
                                :href="project.Url"> 
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                    viewBox="0 0 50 50" stroke-width="1" stroke="currentColor" aria-hidden="true"
                                    data-slot="icon"
                                    class="h-10 w-10 text-[#adb8be] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 cursor-pointer group-hover/link:text-white">
                                    <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M 18.5 2 C 13.81752 2 10 5.8175204 10 10.5 C 10 13.800292 11.949927 16.592855 14.708984 18 C 11.949927 19.407145 10 22.199708 10 25.5 C 10 28.800292 11.949927 31.592855 14.708984 33 C 11.949927 34.407145 10 37.199708 10 40.5 C 10 45.18248 13.81752 49 18.5 49 C 23.18248 49 27 45.18248 27 40.5 L 27 33 L 27 29.65625 C 28.341367 32.201717 30.932066 34 34 34 C 38.406436 34 42 30.406432 42 26 C 42 22.378246 39.526173 19.428685 36.214844 18.449219 C 39.553558 17.301707 42 14.220224 42 10.5 C 42 5.8175204 38.18248 2 33.5 2 L 26 2 L 18.5 2 z M 18.5 4 L 25 4 L 25 17 L 18.5 17 C 14.89848 17 12 14.10152 12 10.5 C 12 6.8984796 14.89848 4 18.5 4 z M 27 4 L 33.5 4 C 37.10152 4 40 6.8984796 40 10.5 C 40 14.10152 37.10152 17 33.5 17 L 27 17 L 27 4 z M 18.5 19 L 25 19 L 25 32 L 18.5 32 C 14.89848 32 12 29.10152 12 25.5 C 12 21.89848 14.89848 19 18.5 19 z M 27 19 L 30.34375 19 C 28.908839 19.756146 27.756146 20.908838 27 22.34375 L 27 19 z M 34 20 C 37.325556 20 40 22.674446 40 26 C 40 29.325554 37.325556 32 34 32 C 30.674444 32 28 29.325554 28 26 C 28 22.674446 30.674444 20 34 20 z M 18.5 34 L 25 34 L 25 40.5 C 25 44.10152 22.10152 47 18.5 47 C 14.89848 47 12 44.10152 12 40.5 C 12 36.89848 14.89848 34 18.5 34 z">
                                    </path>
                                </svg>
                            </a>


                            <a v-if="shouldShowIcon(project.category)" class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#adb7be] hover:border-white group/link"
                                :href="project.projectUrl">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                    viewBox="0 0 30 30" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                    data-slot="icon"
                                    class="h-10 w-10 text-[#adb8be] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 cursor-pointer group-hover/link:text-white">
                                    <path stroke-linecap="round" stroke-linejoin="round"
                                        d="M15,3C8.373,3,3,8.373,3,15c0,5.623,3.872,10.328,9.092,11.63C12.036,26.468,12,26.28,12,26.047v-2.051 c-0.487,0-1.303,0-1.508,0c-0.821,0-1.551-0.353-1.905-1.009c-0.393-0.729-0.461-1.844-1.435-2.526 c-0.289-0.227-0.069-0.486,0.264-0.451c0.615,0.174,1.125,0.596,1.605,1.222c0.478,0.627,0.703,0.769,1.596,0.769 c0.433,0,1.081-0.025,1.691-0.121c0.328-0.833,0.895-1.6,1.588-1.962c-3.996-0.411-5.903-2.399-5.903-5.098 c0-1.162,0.495-2.286,1.336-3.233C9.053,10.647,8.706,8.73,9.435,8c1.798,0,2.885,1.166,3.146,1.481C13.477,9.174,14.461,9,15.495,9 c1.036,0,2.024,0.174,2.922,0.483C18.675,9.17,19.763,8,21.565,8c0.732,0.731,0.381,2.656,0.102,3.594 c0.836,0.945,1.328,2.066,1.328,3.226c0,2.697-1.904,4.684-5.894,5.097C18.199,20.49,19,22.1,19,23.313v2.734 c0,0.104-0.023,0.179-0.035,0.268C23.641,24.676,27,20.236,27,15C27,8.373,21.627,3,15,3z">
                                    </path>
                                </svg>
                            </a>
                        </div>
                    </div>
                    <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                        <h3 class="text-lg font-semibold uppercase lg:text-xl">{{ project.title }}</h3>
                        <p class="text-[#adb7be]">{{ project.desc }}</p>
                        <div class="flex flex-wrap p-2.5">
                            <div v-for="technology in project.technologies" :key="technology"
                                class="text-center px-4 ml-1 mt-1 rounded-3xl bg-[#111827]"
                                style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                                <p class="px-1 py-2">{{ technology }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </ul>
        </div>
    </section>
</template>