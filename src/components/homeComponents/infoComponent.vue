<script setup>
</script>
<template>
    <div class="w-full bg-white rounded-lg p-8 flex flex-col md:mr-auto w-full  sm:mt-10 md:mt-0 relative z-10 shadow-md dark:bg-slate-800 dark:border-2 dark:border-blue-800">
        <h2 class="text-gray-900 text-lg mb-1 font-medium title-font dark:text-white">Info</h2>
        <div class="flex border-t border-gray-200 py-2 ">
            <span class="text-gray-500 dark:text-white">{{ $t('location-title') }}</span>
            <span class="ml-auto text-gray-900 dark:text-white">{{ $t('location') }}</span>
        </div>
        <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500 dark:text-white">{{ $t('experience-title') }}</span>
            <span class="ml-auto text-gray-900 dark:text-white">{{ $t('experience') }}</span>
        </div>
        <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500 dark:text-white">{{ $t('relocation-title') }}</span>
            <span class="ml-auto text-gray-900 dark:text-white">{{ $t('relocation') }}</span>
        </div>
        <div class="flex border-t border-gray-200 py-2">
            <span class="text-gray-500 dark:text-white">email</span>
            <span class="ml-auto text-gray-900 dark:text-white">garcialorenzo1991@gmail.com</span>
        </div>
        <div class="flex border-t border-b mb-6 border-gray-200 py-2">
            <span class="text-gray-500 dark:text-white">{{ $t('phone-title') }}</span>
            <span class="ml-auto text-gray-900 dark:text-white">+5356733933</span>
        </div>
    </div>
</template>