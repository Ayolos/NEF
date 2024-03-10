<template>
    <AppLayout>
        <Head>
            <title>Nord Equipement Fermetures</title>
            <meta name="description" content="Nord Equipement Fermetures est une entreprise spécialisée dans la fabrication et l’installation de divers équipements de fermetures pour les professionnels comme pour les particuliers. La société a été fondée en 1998 sur un principe ; avoir des produits qui allient Qualité, Fiabilité et Esthétisme.">
        </Head>
        <BannerImage :url="data?.imageCollection?.items[0]?.imageAccueil?.url">
            <template #title>
                Bienvenue chez Nord Equipement Fermetures
            </template>
            <template #subtitle>
                <span class="text-curr-black font-bold">Nord Equipement Fermetures</span> est une entreprise spécialisée dans la fabrication et l’installation de divers équipements de fermetures pour les professionnels comme pour les particuliers. La société a été fondée en 1998 sur un principe ; avoir des produits qui allient <span class="text-curr-black font-bold">Qualité, Fiabilité et Esthétisme.</span><br><br>
                Notre dynamique de progrès nous conduit à vous proposer des produits toujours plus performants, pour s’adapter au mieux aux évolutions techniques et à vos besoins. <span class="text-curr-black font-bold">Chez Nord Equipement Fermetures</span>, nous garantissons une réponse adaptée pour des projets allant de la modernisation d’installation pour le particulier, jusqu’aux projets industriels ambitieux.
            </template>
        </BannerImage>
        <div v-if="data" class="md:px-14 px-5 mt-20 md:mt-40 mb-20 md:mb-30 flex flex-col gap-20">
            <div>
                <h1 class="text-4xl text-center font-bold pb-16">Nos différentes prestations</h1>
                <BigCard>
                    <template #section1>
                        <img v-if="data?.homePageCollection?.items[0]?.porteSectionelle?.url" :src="data?.homePageCollection?.items[0]?.porteSectionelle?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                    <template #section2>
                        <img v-if="data?.homePageCollection?.items[0]?.rideauMetallique?.url" :src="data?.homePageCollection?.items[0]?.rideauMetallique?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                    <template #section3>
                        <img v-if="data?.homePageCollection?.items[0]?.grilleEnroulement?.url" :src="data?.homePageCollection?.items[0]?.grilleEnroulement?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                    <template #section4>
                        <img v-if="data?.homePageCollection?.items[0]?.porteRapide?.url" :src="data?.homePageCollection?.items[0]?.porteRapide?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                    <template #section5>
                        <img v-if="data?.homePageCollection?.items[0]?.niveleurQuai?.url" :src="data?.homePageCollection?.items[0]?.niveleurQuai?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                    <template #section6>
                        <img v-if="data?.homePageCollection?.items[0]?.sas?.url" :src="data?.homePageCollection?.items[0]?.sas?.url" alt="" class="w-1/2 mx-auto mt-4 rounded-lg">
                    </template>
                </BigCard>
            </div>
            <section class="py-12 text-justify">
                <h4 class="text-2xl font-bold pb-4">Engagement envers l'Excellence : Des Produits de Qualité et un Service Exceptionnel</h4>
                <p class="mb-3 text-gray-500 dark:text-gray-400">
                    « La satisfaction de nos clients est notre priorité absolue.
                    Parce que toutes nos commandes sont fabriquées à la demande et totalement <span class="text-curr-black font-bold">sur-mesure</span>, il est essentiel que chaque client soit satisfait ; raison pour laquelle je m’engage personnellement sur la <span class="text-curr-black font-bold">qualité</span> de chaque produit qui sort de mon atelier. C’est la grande force de <span class="text-curr-black font-bold">NORD EQUIPEMENT FERMETURES</span> : les personnalisations permettent des compositions uniques, en harmonie avec vos espaces extérieurs et vos envies. Avec <span class="text-curr-black font-bold">NORD EQUIPEMENT FERMETURES</span>, vous avez une véritable liberté de choix ! Nos conseillers sont à votre disposition pour vous guider sur les tendances actuelles et transformer votre envie en projet concret. Ensuite, c’est à nous de mériter votre <span class="text-curr-black font-bold">confiance</span> ! »
                </p>
                <p class="mb-3 text-gray-500 dark:text-gray-400 text-end">Richard TAHON Fondateur de NORD EQUIPEMENT FERMETURES</p>
            </section>
            <Caroussel :images="data.homePageCollection.items.map(item => item.carrouselCollection.items.map(carouselItem => carouselItem.url)).flat()"></Caroussel>
        </div>
    </AppLayout>
</template>
<script setup>
import {ref, onMounted, onUnmounted, onBeforeUnmount} from 'vue';
import BannerImage from "@/Components/App/Banner/BannerImage.vue";
import AppLayout from "@/Layouts/AppLayout.vue";
import Caroussel from "@/Components/App/Caroussel/Caroussel.vue";
import BigCard from "@/Components/App/Card/BigCard.vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";
import { Head } from '@inertiajs/vue3'
// Import other components...

const query = `{
      homePageCollection{
        items{
         carrouselCollection{
          items{
            url
            }
          }
          porteRapide {url}
          rideauMetallique {url}
          niveleurQuai {url}
          grilleEnroulement {url}
          sas {url}
          porteSectionelle {url}
        }
      }
}`;


const {data, isLoading} = useContentfulFetch(query)


const isWindowBelow735 = ref(window.innerWidth < 735);

const handleResize = () => {
    isWindowBelow735.value = window.innerWidth < 735;
};

onMounted(() => {
    window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
    window.removeEventListener('resize', handleResize);
});
</script>
