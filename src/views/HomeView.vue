<script setup>
import { ref } from 'vue'
import bgProfile from '@/assets/images/bg-profile-d.jpg'
import profile from '@/assets/images/profile.jpeg'
import smart from '@/assets/images/smart.jpg'
import eti from '@/assets/images/eti.jpg'
import avanze from '@/assets/images/avanze.jpg'
import ipi from '@/assets/images/ipi.jpg'
import cujae from '@/assets/images/cujae.jpg'
import uci from '@/assets/images/uci.jpg'
import enLogo from '@/assets/images/eng.jpg'
import esLogo from '@/assets/images/spain.jpg'
let openTab = ref(1)

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
let skills = ref(['Laravel', 'Vue', 'Python', 'SQL', 'Open CV', 'Cypress'])
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

let activeMenu = ref(1);
</script>

<template>
  <div class="grid grid-cols-3">
    <div>
      <div class="container py-10 mx-auto flex flex-col">
        <div
          class="w-full bg-white rounded-lg flex flex-col md:mr-auto w-full mt-10 md:mt-0 relative z-10 shadow-md mb-10">
          <img class="w-full rounded-t-md" :src="bgProfile">
          <div>
            <img :src="profile" class="rounded-full w-60 -mt-32 mx-auto border-8 border-white">
          </div>
          <div class="px-6 py-4">
            <h2 class="text-gray-900 text-lg mb-1 font-medium title-font">{{ $t("name") }}</h2>
            <p class="text-gray-700 text-base">
              {{ $t("title") }} : {{ $t("country") }}
            </p>
            <p class="text-gray-700 text-base py-2">
              {{ $t("resume") }}
            </p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
              v-for="skill in skills">{{ skill }}</span>
          </div>
          <button
            class="m-5 text-white bg-indigo-500 border-0 py-2 px-6 focus:outline-none hover:bg-indigo-600 rounded text-lg">
            Download CV
            <fa icon="download" />
          </button>
        </div>
        <div
          class="w-full bg-white rounded-lg p-8 flex flex-col md:mr-auto w-full mt-10 md:mt-0 relative z-10 shadow-md mb-10">
          <h2 class="text-gray-900 text-lg mb-1 font-medium title-font">About Me</h2>
          <p class="leading-relaxed mb-5 text-gray-600">
            {{ $t('about-me') }}
          </p>
        </div>
        <div
          class="w-full bg-white rounded-lg p-8 flex flex-col md:mr-auto w-full mt-10 md:mt-0 relative z-10 shadow-md">
          <h2 class="text-gray-900 text-lg mb-1 font-medium title-font">Info</h2>
          <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500">{{ $t('location-title') }}</span>
            <span class="ml-auto text-gray-900">{{ $t('location') }}</span>
          </div>
          <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500">{{ $t('experience-title') }}</span>
            <span class="ml-auto text-gray-900">{{ $t('experience') }}</span>
          </div>
          <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500">{{ $t('relocation-title') }}</span>
            <span class="ml-auto text-gray-900">{{ $t('relocation') }}</span>
          </div>
          <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500">email</span>
            <span class="ml-auto text-gray-900">garcialorenzo1991@gmail.com</span>
          </div>
          <div class="flex border-t border-b mb-6 border-gray-200 py-2">
            <span class="text-gray-500">{{ $t('phone-title') }}</span>
            <span class="ml-auto text-gray-900">56733933</span>
          </div>
        </div>
      </div>
    </div>

    <div class="col-span-2">
      <div class="container py-10 flex flex-col mx-8">
        <!-- Menu -->
        <div class="w-full flex flex-wrap space-x-12">
          <div class="w-3/5 mb-4 flex space-x-4 p-2 bg-white rounded-lg shadow-md">
            <button @click="openTab = 1" :class="{ 'bg-indigo-500 text-white': openTab === 1 }"
              class="text-gray-800 capitalize flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300 hover:bg-indigo-200">{{
                $t('experience-title') }} & {{ $t('education-title') }} </button>
            <button @click="openTab = 2" :class="{ 'bg-indigo-500 text-white': openTab === 2 }"
              class="text-gray-800 capitalize flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300 hover:bg-indigo-200">{{
                $t('projects-title') }}</button>
          </div>
          <div class="w-1/8 cursor-pointer transition-all duration-300" v-if="$i18n.locale == 'en'" @click="$i18n.locale = 'es'">
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
              <div class="peer flex h-14 items-center gap-8 rounded-md bg-orange-600 
              px-5 after:absolute after:h-14 after:w-1/2 after:left-0 
              after:rounded-md after:left after:bg-white/40 after:transition-all
              after:content-[''] peer-checked:bg-yellow-500 
              peer-checked:after:translate-x-14 peer-focus:outline-none 
              dark:border-slate-600 dark:bg-slate-700 text-sm text-white">
                <span>
                  <fa icon="moon" size="xl" />
                </span>
                <span>
                  <fa icon="sun" size="xl" />
                </span>
              </div>
            </label>
          </div>
        </div>

        <!-- Experiences -->
        <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5" v-show="openTab == 1">
          <div class="w-full bg-gray-100">
            <h2 class="text-gray-900 text-lg mb-1 font-medium title-font py-2 px-5 capitalize">
              {{ $t('experience-title') }}</h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100 p-8 rounded" v-for="experience in experiences">
              <a class="inline-flex items-center">
                <img alt="testimonial" :src="experience.logo"
                  class="w-16 h-16 rounded-full flex-shrink-0 object-cover object-center" />
                <span class="flex-grow flex flex-col pl-4">
                  <span class="title-font font-medium text-gray-900">{{ experience.name }} | {{ experience.location }} -
                    {{
                      experience.to }}</span>
                  <span class="text-gray-500 text-sm uppercase">{{ experience.position }} </span>
                </span>
              </a>
            </div>
          </div>
        </div>

        <!-- Education -->
        <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5" v-show="openTab == 1">
          <div class="w-full bg-gray-100">
            <h2 class="text-gray-900 text-lg mb-1 font-medium title-font py-2 px-5 capitalize">
              {{ $t('education-title') }}</h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100 p-8 rounded" v-for="education in educations">
              <a class="inline-flex items-center">
                <img alt="testimonial" :src="education.logo"
                  class="w-16 h-16 rounded-full flex-shrink-0 object-cover object-center" />
                <span class="flex-grow flex flex-col pl-4">
                  <span class="title-font font-medium text-gray-900">{{ education.title }} | {{ education.location
                    }}</span>
                  <span class="text-gray-500 text-sm uppercase">{{ education.center }} </span>
                </span>
              </a>
            </div>
          </div>
        </div>

        <!-- Projects -->
        <div class="w-full relative bg-white p-2 shadow-xl mx-auto w-full rounded-2xl m-5" v-show="openTab == 2">
          <div class="w-full bg-gray-100">
            <h2 class="text-gray-900 text-lg mb-1 font-medium title-font py-2 px-5 capitalize">{{ $t('education-title')
              }}
            </h2>
            <hr>
            </hr>
            <div class="h-full bg-gray-100 p-8 rounded" v-for="experience in experiences">
              <a class="inline-flex items-center">
                <img alt="testimonial" :src="experience.logo"
                  class="w-16 h-16 rounded-full flex-shrink-0 object-cover object-center" />
                <span class="flex-grow flex flex-col pl-4">
                  <span class="title-font font-medium text-gray-900">{{ experience.name }} | {{ experience.from }} - {{
                    experience.to }}</span>
                  <span class="text-gray-500 text-sm uppercase">{{ experience.position }} </span>
                </span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
