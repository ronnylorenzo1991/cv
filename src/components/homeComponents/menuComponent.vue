<script setup>
import { defineProps } from 'vue'
import enLogo from '@/assets/images/eng.jpg'
import esLogo from '@/assets/images/spain.jpg'
import { useDark, useToggle } from '@vueuse/core'
const isDark = useDark();

const toggleDark = useToggle(isDark);
const props = defineProps({
    openTab: {
        default: 1
    }
})
</script>
<template>
    <div class="w-full flex flex-wrap lg:space-x-8 max-w-full z-50 lg:justify-between">
        <div class="fixed top-0 lg:relative flex py-2 sm:py-2 lg:py-0 space-x-7">
            <div class="w-1/8 cursor-pointer transition-all duration-300" v-if="$i18n.locale == 'en'"
                @click="$i18n.locale = 'es'">
                <img :src="enLogo" class="w-16 rounded-md absolute py-2">
                <img :src="esLogo" class="w-16 rounded-md mx-2">
            </div>
            <div class="w-1/8 cursor-pointer transition-all duration-300" v-if="$i18n.locale == 'es'">
                <img :src="esLogo" class="w-16 rounded-md absolute py-2" @click="$i18n.locale = 'en'">
                <img :src="enLogo" class="w-16 rounded-md mx-2">
            </div>
            <div class="w-1/8">
                <label class="relative inline-flex cursor-pointer items-center">
                    <input type="checkbox" value="" checked class="peer sr-only" />
                    <div @click="toggleDark()" class="peer flex h-14 items-center gap-8 rounded-md bg-white
            px-5 after:absolute after:h-14 after:w-1/2 after:left-0 
            after:rounded-md after:left after:bg-white/40 after:border-2 dark:after:border-0 after:transition-all
            after:content-[''] 
            peer-checked:after:translate-x-14 peer-focus:outline-none 
            dark:border-blue-800 border-2 dark:bg-gray-800 text-sm text-white">
                        <span>
                            <fa icon="sun" size="xl" class="dark:text-white text-[orange]" />
                        </span>
                        <span>
                            <fa icon="moon" size="xl" class="dark:text-[yellow] text-[black]" />
                        </span>
                    </div>
                </label>
            </div>
        </div>
        <div
            class="w-full lg:w-3/5 mb-4 flex space-x-4 p-2 bg-white rounded-lg shadow-md  dark:bg-slate-800 dark:border-blue-800 dark:border-2">
            <button @click="$emit('toggleMenu', 1)" :class="{ 'bg-indigo-500 text-white': openTab === 1 }"
                class="text-gray-800 dark:text-white capitalize flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue focus:ring-0 transition-all duration-300 hover:bg-indigo-200">{{
                    $t('experience-title') }} & {{ $t('education-title') }} </button>
            <button @click="$emit('toggleMenu', 2)" :class="{ 'bg-indigo-500 text-white': openTab === 2 }"
                class="text-gray-800 dark:text-white capitalize flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300 hover:bg-indigo-200">{{
                    $t('projects-title') }}</button>
        </div>
    </div>
</template>