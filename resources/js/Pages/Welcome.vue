<template>
    <AppLayout>
        <BannerImage :url="data?.imageCollection?.items[0]?.imageAccueil?.url">
            <template #title>
                Bienvenue chez Nord Equipement Fermetures
            </template>
            <template #subtitle>
                <span class="text-curr font-bold">Nord Equipement Fermetures</span> est spécialisés dans la fabrication et l'installation de divers équipements de fermeture pour les professionnels et les particuliers. Avec notre expertise et notre savoir-faire, nous vous offrons des solutions sur mesure pour répondre à vos besoins en matière de sécurité et de confort.
            </template>
        </BannerImage>
        <div v-if="data" class="md:px-14 px-5 mt-20 md:mt-40 mb-20 md:mb-30 flex flex-col gap-20">
            <div>
                <h1 class="text-4xl text-center font-bold pb-16">Nos différentes prestations</h1>
                <BigCard></BigCard>
            </div>
            <section class="py-12">
                <h4 class="text-2xl font-bold pb-4">Engagement envers l'Excellence : Des Produits de Qualité et un Service Exceptionnel</h4>
                <p class="mb-3 text-gray-500 dark:text-gray-400">
                    Chez Nord Equipement Fermetures, nous croyons fermement en l'excellence à tous les niveaux de notre service. Notre engagement envers la qualité commence dès la conception de nos produits. Nous sélectionnons soigneusement les meilleurs matériaux et nous nous assurons que nos équipements de fermeture sont fabriqués selon les normes les plus strictes de l'industrie. Cette attention méticuleuse aux détails garantit que nos produits sont durables, fiables et offrent une performance optimale tout au long de leur cycle de vie.</p>
                <p class="mb-3 text-gray-500 dark:text-gray-400">En plus de nos produits de haute qualité, nous attachons une importance primordiale à offrir un service exceptionnel à chaque client. Notre équipe dévouée est composée d'experts compétents et expérimentés qui sont là pour vous guider à chaque étape du processus, de la consultation initiale à l'installation et au-delà. Nous comprenons que chaque projet est unique, c'est pourquoi nous travaillons en étroite collaboration avec vous pour comprendre vos besoins spécifiques et vous proposer des solutions sur mesure qui répondent parfaitement à vos attentes.</p>
                <p class="mb-3 text-gray-500 dark:text-gray-400">Votre satisfaction est notre priorité absolue. C'est pourquoi nous nous efforçons de fournir un service client exceptionnel à chaque interaction. Nous sommes là pour répondre à toutes vos questions, résoudre tous vos problèmes et vous assurer une expérience sans souci du début à la fin. Chez Nord Equipement Fermetures, nous sommes fiers de la réputation que nous avons acquise pour notre engagement envers l'excellence et notre dévouement à la satisfaction de nos clients.
                </p>
            </section>
            <Caroussel :images="data.homePageCollection.items.map(item => item.carrouselCollection.items.map(carouselItem => carouselItem.url)).flat()"></Caroussel>
        </div>
        <Footer></Footer>
    </AppLayout>
</template>
<script setup>
import {ref, onMounted, onUnmounted} from 'vue';
import BannerImage from "@/Components/App/Banner/BannerImage.vue";
import AppLayout from "@/Layouts/AppLayout.vue";
import Caroussel from "@/Components/App/Caroussel/Caroussel.vue";
import BigCard from "@/Components/App/Card/BigCard.vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";
// Import other components...

const query = `{
    homePageCollection{
    items{
     carrouselCollection{
      items{
        url
        }
      }
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
