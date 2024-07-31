<script setup>
import { ref } from 'vue'
import bgProfile from '@/assets/images/bg-profile-d.jpg'
import bgProfileDark from '@/assets/images/bg-profile-dark.jpg'
import profile from '@/assets/images/profile.jpeg'
let skills = ref(['Laravel', 'Vue', 'Python', 'SQL', 'Open CV', 'Cypress'])

</script>
<template>
    <div class="w-full bg-white rounded-lg flex flex-col md:mr-auto
               sm:mt-10 md:mt-0 relative z-10 shadow-md mb-10 dark:bg-slate-800 dark:border-2 dark:border-blue-800">
        <img class="w-full rounded-t-md hidden dark:block" :src="bgProfileDark">
        <img class="w-full rounded-t-md dark:hidden" :src="bgProfile">
        <div>
            <img :src="profile" class="rounded-full w-60 -mt-32 mx-auto border-8 border-white">
        </div>
        <div class="px-6 py-4">
            <h2 class="text-gray-900 dark:text-white text-lg mb-1 font-medium title-font">{{ $t("name") }}</h2>
            <p class="text-gray-700 dark:text-white text-base">
                {{ $t("title") }} : {{ $t("country") }}
            </p>
            <p class="text-gray-700 dark:text-white text-base py-2">
                {{ $t("resume") }}
            </p>
        </div>
        <div class="px-6 pt-4 pb-2">
            <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                v-for="skill in skills">{{ skill }}</span>
        </div>
        <button
            class="m-5 text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded text-lg">
            {{ $t('download-title') }} CV
            <fa icon="download" />
        </button>
    </div>
</template>