<script setup>
import { computed } from 'vue'
import cv from '@/assets/images/cv.jpg'
import ulau from '@/assets/images/ulau.jpg'
import flask from '@/assets/images/flask.jpg'
import { useI18n } from 'vue-i18n'
const { t } = useI18n()

const projects = computed(() => {
  return [
    {
      name: t('cv-name'),
      description: t('cv-description'),
      tags: ['vue3', 'tailwind', 'css'],
      image: cv,
      github: 'https://github.com/ronnylorenzo1991/cv',
    },
    {
      name: t('ulau-name'),
      description: t('ulau-description'),
      tags: ['laravel', 'tailwind', 'vue3'],
      image: ulau,
      github: 'https://github.com/ronnylorenzo1991/ulau',
    },
    {
      name: t('flask-name'),
      description: t('flask-description'),
      tags: ['flask', 'opencv', 'python'],
      image: flask,
      github: 'https://github.com/ronnylorenzo1991/api-flask-opencv-detection',
    }
  ]
})
</script>
<template>
    <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5 dark:bg-slate-800 dark:border-2 dark:border-blue-800">
        <div class="w-full bg-gray-100 dark:bg-slate-800">
            <h2 class="text-gray-900 dark:text-white text-lg mb-1 font-medium title-font py-2 px-5 capitalize">
                {{ $t('projects-title') }}
            </h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100 dark:bg-slate-800 sm:p-8 rounded" v-for="project in projects">
                <a class="sm:inline-flex sm:items-center">
                    <img alt="testimonial" :src="project.image" class="w-16 h-16 rounded-full object-cover sm:mb-20 my-6 mx-auto sm:mx-2 shadow-xl" />
                    <span class="flex-grow flex flex-col pl-4">
                        <span class="title-font font-medium text-gray-900 dark:text-white">{{ project.name }} </span>
                        <span class="text-gray-500 dark:text-white text-sm">{{ project.description }} </span>
                        <a class="text-blue-500 text-sm" :href="project.github">{{ project.github }} </a>
                        <div class="pt-4 pb-2">
                            <span
                                class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                                v-for="tag in project.tags">{{ tag }}</span>
                        </div>
                    </span>
                </a>
            </div>
        </div>
    </div>
</template>