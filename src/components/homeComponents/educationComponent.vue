<script setup>
import { ref } from 'vue'
import ipi from '@/assets/images/ipi.jpg'
import cujae from '@/assets/images/cujae.jpg'
import uci from '@/assets/images/uci.jpg'
let educations = ref([
    {
        title: 'Técnico de Nivel Medio en Informática',
        center: 'IPI Mártires de Girón',
        location: 'La Habana. Cuba',
        logo: ipi,
    },
    {
        title: 'Ingeniería en Ciencias Informáticas',
        center: 'Universidad de Ciencias Informáticas',
        location: 'La Habana. Cuba',
        logo: uci,
    },
    {
        title: 'Especialista en Aplicaciónes Criptográficas',
        center: 'CUJAE',
        location: 'La Habana. Cuba',
        logo: cujae,
    },
])
</script>
<template>
    <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5 dark:bg-slate-800 dark:border-2 dark:border-blue-800">
        <div class="w-full bg-gray-100 dark:bg-slate-800">
            <h2 class="text-gray-900 dark:text-white text-lg mb-1 font-medium title-font py-2 px-5 capitalize">
                {{ $t('education-title') }}</h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100 dark:bg-slate-800 sm:p-8 rounded pb-5" v-for="education in educations">
                <a class="sm:inline-flex sm:items-center">
                    <img alt="testimonial" :src="education.logo"
                        class="w-16 h-16 rounded-full object-cover mx-auto my-6 sm:mx-2 shadow-xl sm:my-0" />
                    <span class="flex-grow flex flex-col pl-4">
                        <span class="title-font font-medium text-gray-900  dark:text-white">{{ education.title }} | {{ education.location
                            }}</span>
                        <span class="text-gray-500 dark:text-gray-300 text-sm uppercase">{{ education.center }} </span>
                    </span>
                </a>
            </div>
        </div>
    </div>
</template>