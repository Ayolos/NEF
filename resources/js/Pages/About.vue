<script setup>

import AppLayout from "@/Layouts/AppLayout.vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";
import { Head } from '@inertiajs/vue3'

const query = `{
     aboutPageCollection{
    items{
      mainImage{url}
      sectionImage{url}
    }
  }
}`;


const {data, isLoading} = useContentfulFetch(query)
</script>

<template>
<AppLayout v-if="data">
    <Head>
        <title>A propos de nous</title>
        <meta name="description" content="Découvrer plus sur NORD EQUIPEMENT FERMETURES">
    </Head>
    <section class="h-full flex md:flex-row flex-col gap-14 justify-center items-center py-20 px-10 sm:px-20">
        <div class="flex flex-col gap-5 pt-9 text-justify">
            <h1 class="font-bold text-3xl md:text-5xl pb-8">A propos de nous</h1>
            <h1 class="font-bold text-xl ">NORD EQUIPEMENT FERMETURES</h1>
            <p class="text-gray-500 sm:text-lg text-sm text-justify">
                <span class="text-curr-black font-bold">Expert de la fermeture</span>, nous vous accompagnons dans toutes les étapes de votre projet, de la conception à la pose de vos menuiseries. <span class="text-curr-black font-bold">Alliant qualité, fiabilité et esthétisme</span>, les produits que nous proposons sont performants et répondent au mieux à vos besoins au quotidien. Grâce aux diverses compétences qu’elle rassemble, l’entreprise est ainsi capable gérer l’ensemble de vos besoins dans le domaine de la fermeture.
            </p>
        </div>
        <img class="rounded md:w-1/2 md:h-full h-[30vh] object-cover shadow-2xl" :src="data?.aboutPageCollection?.items[0]?.mainImage?.url" alt="Extra large avatar">
    </section>
    <hr class="border-1 border-gray-300">
    <section class="h-full flex flex-col gap-14 items-start p-5 lg:p-20 mb-20">
        <h1 class="font-bold text-3xl md:text-4xl pt-10">Notre Engagement</h1>
        <div class="w-full h-full md:flex-row flex-col flex gap-16 justify-center items-center">
            <img :src="data?.aboutPageCollection?.items[0]?.sectionImage?.url" class="w-1/2 overflow-clip rounded-xl" alt="image principal" />
            <div class="basis-1/2 gap-4 flex flex-col text-justify">
                <p class="text-gray-500">
                    Tous nos produits sont <span class="text-curr-black font-bold">faits sur mesure</span>. Nous prenons le temps d’analyser chaque commande afin de répondre aux attentes de nos clients du mieux que nous le pouvons.
                </p>
                <h1 class="font-bold text-xl">Engagement envers la Qualité</h1>
                <p class="text-gray-500">
                    Nos produits sont produits à l’aide de matériaux de très bonne qualité et passent un <span class="text-curr-black font-bold">test de qualité complet</span> avant de sortir de l’usine. Nos produits répondent aux normes de qualité les plus élevées.
                    Nos clients peuvent identifier la couleur de leur choix figurant dans <span class="text-curr-black font-bold">la palette RAL</span>.
                </p>
                <h1 class="font-bold text-xl">Engagement envers la Satisfaction du Client</h1>
                <p class="text-gray-500">
                    Si chacun de nos projets est unique, notre manière de construire nos opérations reste fidèle à nos valeurs : <span class="text-curr-black font-bold">Responsable et Engagé</span>.
                </p>
            </div>
        </div>
    </section>
</AppLayout>
</template>

<style scoped>

</style>
