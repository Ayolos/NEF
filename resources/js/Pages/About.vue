<script setup>

import AppLayout from "@/Layouts/AppLayout.vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";

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
    <section class="h-full flex md:flex-row flex-col gap-14 justify-center pb-20 md:pt-20 items-center px-10 sm:px-20">
        <div class="flex flex-col gap-5 w-full pt-9">
            <h1 class="font-bold text-3xl md:text-5xl pb-8">A propos de nous</h1>
            <h1 class="font-bold text-xl ">NORD EQUIPEMENT FERMETURES</h1>
            <p class="text-gray-500 sm:text-lg text-sm">
                Nord Equipement Fermetures est bien plus qu'une entreprise de fermetures. Nous sommes votre partenaire de confiance pour tous vos besoins en matière de sécurité et de fonctionnalité des accès, que ce soit pour votre domicile, votre entreprise ou vos installations industrielles. Notre engagement envers l'excellence et l'innovation se reflète dans chaque produit que nous fabriquons et dans chaque service que nous fournissons.
            </p>
        </div>
        <img class="rounded md:w-1/2 h-full shadow-2xl" :src="data?.aboutPageCollection?.items[0]?.mainImage?.url" alt="Extra large avatar">
    </section>
    <hr class="border-1 border-gray-300">
    <section class="h-full flex flex-col gap-14 items-start p-5 lg:p-20 mb-20">
        <h1 class="font-bold text-3xl md:text-4xl pt-10">Notre Engagement</h1>
        <div class="w-full h-full md:flex-row flex-col flex gap-16 justify-center items-center">
            <img :src="data?.aboutPageCollection?.items[0]?.sectionImage?.url" class="w-1/2 overflow-clip rounded-xl" alt="image principal" />
            <div class="basis-1/2 gap-4 flex flex-col">
                <p class="">
                    Chez Nord Equipement Fermetures, nous sommes fiers de notre engagement envers nos clients, nos produits et nos valeurs. Nous nous engageons à être votre partenaire de confiance pour tous vos besoins en matière de fermeture.                </p>
                <h1 class="font-bold text-xl">Engagement envers la Qualité</h1>
                <p class="">
                    Nous sommes fiers de la qualité de nos produits et services. Chaque produit que nous fabriquons et installons est soumis à des normes rigoureuses de contrôle qualité pour garantir sa durabilité et sa fiabilité.
                </p>
                <h1 class="font-bold text-xl">Engagement envers la Satisfaction du Client</h1>
                <p class="">
                    La satisfaction de nos clients est notre priorité absolue. Nous nous efforçons de comprendre leurs besoins uniques et de leur fournir des solutions sur mesure qui dépassent leurs attentes.                </p>

            </div>
        </div>
    </section>
</AppLayout>
</template>

<style scoped>

</style>
