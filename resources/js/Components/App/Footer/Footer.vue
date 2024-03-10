<script setup>

import HeaderItem from "@/Components/App/Header/HeaderItem.vue";
import Logo from '/public/Logo.png'
import Logo2 from '/public/Logo2.png'

</script>

<template>
    <div class="bg-gray-200">
        <div class="w-full">
            <div class="flex sm:items-center items-start justify-between px-8">
                <img :src="Logo2" class="sm:h-12 h-8" alt="Logo" />
                <ul class="flex flex-wrap items-center justify-center mb-6 text-sm font-medium text-gray-500 sm:mb-0">
                    <header-item href="/" class="text-xs">Accueil</header-item>
                    <header-item :href="route('services')" class="text-xs">Services</header-item>
                    <header-item :href="route('about')" class="text-xs">About</header-item>
                    <header-item :href="route('contact')" class="text-xs">Contact</header-item>
                </ul>
                <img :src="Logo" class="sm:h-12 h-8" alt="Logo" />
            </div>
            <hr class="my-6 border-gray-500 sm:mx-auto lg:my-8" />
            <span class="block text-sm text-center pb-5 text-gray-500 sm:text-center dark:text-gray-400">© 2023 <a href="" class="hover:underline">Nord France Fermetures™</a>. Tout les droits sont réservé.</span>
        </div>
    </div>
</template>

<style scoped>

</style>
