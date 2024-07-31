<script setup>
import { ref } from 'vue'
import resume from '@/components/homeComponents/resumeComponent.vue'
import about from '@/components/homeComponents/aboutComponent.vue'
import info from '@/components/homeComponents/infoComponent.vue'
import experience from '@/components/homeComponents/experienceComponent.vue'
import education from '@/components/homeComponents/educationComponent.vue'
import projects from '@/components/homeComponents/projectsComponent.vue'
import menuComponent from '@/components/homeComponents/menuComponent.vue'

let openTab = ref(1)
const toggleMenu = (value) => {
  openTab.value = value
}

</script>

<template>
  <div class="grid lg:grid-cols-3 grid-cols-1">
    <div>
      <div class="container py-10 mx-auto flex flex-col">
        <resume />
        <about />
        <info />
      </div>
    </div>

    <div class="col-span-2">
      <div class="container lg:py-10 mx-auto lg:mx-8 flex flex-col justify-between">
        <menu-component @toggleMenu="toggleMenu" :openTab="openTab" />
        <experience v-show="openTab == 1" />
        <education v-show="openTab == 1" />
        <projects v-show="openTab == 2" />
      </div>
    </div>
  </div>
</template>
