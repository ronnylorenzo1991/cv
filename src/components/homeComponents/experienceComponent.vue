<script setup>
import { ref } from 'vue'
import smart from '@/assets/images/smart.jpg'
import eti from '@/assets/images/eti.jpg'
import avanze from '@/assets/images/avanze.jpg'

let experiences = ref([
    {
        name: 'Empresa de tecnologías de la Información ETI (Cuba)',
        from: '6/2018',
        to: '6/2020',
        logo: eti,
        position: 'Especialista A en ciencias informáticas',
    },
    {
        name: 'MRO Smart 145 (Miami USA)',
        from: '7/2020',
        to: '6/2021',
        logo: smart,
        position: 'Desarrollador A',
    },
    {
        name: 'Grupo Avanze (Puerto M. Chile)',
        from: '7/2021',
        to: '8/2024',
        logo: avanze,
        position: 'Freelance Desarrollador',
    },
])
</script>
<template>
    <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5 dark:bg-slate-800 dark:border-2 dark:border-blue-800">
        <div class="w-full bg-gray-100 dark:bg-slate-800">
            <h2 class="text-gray-900 dark:text-white text-lg mb-1 font-medium title-font py-2 px-5 capitalize">
                {{ $t('experience-title') }}</h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100  dark:bg-slate-800 sm:p-8 rounded pb-5" v-for="experience in experiences">
                <a class="sm:inline-flex sm:items-center">
                    <img alt="testimonial" :src="experience.logo"
                        class="w-16 h-16 rounded-full object-cover mx-auto my-6 sm:mx-2 shadow-xl sm:my-0" />
                    <span class="flex-grow flex  flex-col pl-4">
                        <span class="title-font dark:text-white font-medium text-gray-900">{{ experience.name }} | {{
                            experience.location }} -
                            {{
                                experience.to }}</span>
                        <span class="text-gray-500 dark:text-gray-300 text-sm uppercase">{{ experience.position }} </span>
                    </span>
                </a>
            </div>
        </div>
    </div>
</template>