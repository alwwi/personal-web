<script setup>
import {defineAsyncComponent} from 'vue';

const NavBars = defineAsyncComponent(() => import('@/components/NavBars.vue'));
const HeroSection = defineAsyncComponent(() => import('@/components/HeroSection.vue'));
const AboutSection = defineAsyncComponent(() => import('@/components/AboutSection.vue'));
const Experience = defineAsyncComponent(() => import('@/components/Experience.vue'));
const Project = defineAsyncComponent(() => import('@/components/ProjectSection.vue'));
const Contact = defineAsyncComponent(() => import('@/components/ContactSection.vue'));
const Footer = defineAsyncComponent(() => import('@/components/Footer.vue'));
const BacktoTop = defineAsyncComponent(() => import('@/components/BacktoTop.vue'));
</script>

<template>
  <div class="bg-[#111827] min-h-screen">
    <NavBars /> 
    <HeroSection /> 
    <AboutSection />
    <Experience /> 
    <Project /> 
    <Contact /> 
    <Footer /> 
    <BacktoTop /> 
  </div>
</template>
