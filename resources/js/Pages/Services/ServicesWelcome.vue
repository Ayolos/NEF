<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import {onMounted, onUnmounted, ref} from "vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";
import { Head } from '@inertiajs/vue3'

const query = `{
   servicePageCollection{
    items {
      cardImgCollection{
        items{
          url
        }
      }
      catalogCollection{
        items{
          url
        }
      }
    }
  }
}`;


const {data, isLoading} = useContentfulFetch(query)


const isWindowBelow735 = ref(window.innerWidth < 1000);

const handleResize = () => {
    isWindowBelow735.value = window.innerWidth < 1000;
};

onMounted(() => {
    window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
    window.removeEventListener('resize', handleResize);
});

</script>

<template>
    <Head>
        <title>Nos Services</title>
        <meta name="description" content="Découvrer nos différents services">
    </Head>
    <AppLayout v-if="data">
        <div class="md:pt-20 md:px-20 p-8">
            <h1 class="text-3xl font-bold pb-16">Découvrer nos différents services</h1>

            <div class="grid sm:grid-cols-2 gap-8">
                <div class="bg-gray-200 shadow-xl rounded-xl text-curr h-max min-h-full">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[0]?.url" class="w-full h-1/2 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8 text-justify h-full">
                        <h1 class="font-bold text-xl pb-2 text-gray-900 text-center">Portes Sectionnelle</h1>
                        <div class="flex flex-col gap-3">
                            <p>
                                Nos portes de garage sont fabriquées sur mesure pour répondre à tous vos besoins.
                                Modernes par leur design et solides par leur composition, <span class="text-curr-black font-bold">nos portes de garage</span> sont ce qui se fait de mieux dans le domaine.
                            </p>
                            <p>
                                <span class="text-curr-black font-bold">Nous proposons 3 types d’ouvertures</span> selon vos besoins:
                            </p>
                            <ul class="list-disc pl-3">
                                <li>Portes sectionnelles Plafond</li>
                                <li>Portes sectionnelles Latérales</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl rounded-xl text-curr h-max min-h-full">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[1]?.url" class="w-full h-1/2 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8 text-justify">
                        <h1 class="font-bold text-xl pb-2 text-gray-900 text-center">Portails et Extérieurs</h1>
                        <div class="flex flex-col gap-3">
                            <p>
                                Délimitez votre propriété avec style et harmonie.
                            </p>
                            <p>
                                Nous privilégions des <span class="text-curr-black font-bold">matériaux étanches et résistants</span> comme l’aluminium et le PVC afin d’assurer la pérennité et la longévité de la clôture.
                            </p>
                            <p>
                                Spécialisés dans la fabrication de menuiseries sur mesure, nous vous proposons une grande variété de modèles et de coloris pour une parfaite harmonisation avec <span class="text-curr-black font-bold">le portail</span> ou <span class="text-curr-black font-bold">le portillon</span>.
                            </p>
                            <ul class="list-disc pl-3">
                                <li>Les portails</li>
                                <li>Les clôtures</li>
                                <li>Les claustras</li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl rounded-xl text-curr h-max min-h-full">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[2]?.url" class="w-full h-1/2 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8 text-justify">
                        <h1 class="font-bold text-xl pb-2 text-gray-900 text-center">Et pour les Industriels</h1>
                        <div class="flex flex-col gap-3">
                            <p>
                                <span class="text-curr-black font-bold">Nord Equipement Fermetures</span> est également capable de répondre à la demande des industriels : bâtiment industriel, bâtiment de stockage, bâtiment isotherme, station de tri et de conditionnement, Grande et Moyenne Surface ...
                            </p>
                            <p>
                                Une <span class="text-curr-black font-bold">gamme complète</span>, permettant de répondre à l’intégralité de vos besoins :
                            </p>
                            <ul class="list-disc pl-3">
                                <li>Portes sectionnelles</li>
                                <li>Portails</li>
                                <li>Rideaux métalliques</li>
                                <li>Grille à enroulement</li>
                                <li>Portes rapides souples</li>
                                <li>Niveleur de quai</li>
                                <li>Sas d’étanchéité</li>
                                <li>Automatisme de fermetures</li>
                            </ul>

                        </div>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl text-center rounded-xl text-curr h-max min-h-full">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[3]?.url" class="w-full h-1/2 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8 text-justify">
                        <h1 class="font-bold text-xl pb-2 text-gray-900">Options Diverses</h1>
                        <p>
                            Nous proposons également une gamme d'options pour <span class="text-curr-black font-bold">personnaliser</span> vos équipements de fermetures, y compris des boites à clef, des digicodes, des émetteurs, récepteurs, armoire de commande etc ...
                        </p>
                    </div>
                </div>
            </div>

            <section class="py-24">
                <div class="py-24 text-justify">
                    <h4 class="text-2xl font-bold pb-4 text-center mb-4">Contactez-nous pour une consultation personnalisée</h4>
                    <p class="mb-3 text-gray-500">
                        Votre maison ou votre établissement nécessite l’installation d’une nouvelle porte de garage ? Vous êtes à la recherche d’un installateur de portes de garage à faible encombrement ? <span class="text-curr-black font-bold">Nord Equipement Fermetures</span> est à votre écoute pour votre projet de construction ou de rénovation. Nous proposons une large gamme de portes de garages, adaptées à tous les styles et tous les budgets.
                    </p>
                    <p class="mb-3 text-gray-500">
                        Vous souhaitez profiter de votre jardin en toute sérénité ? La clôture permet de créer une continuité sécurisante en périphérie du terrain, du jardin ou de la piscine. <span class="text-curr-black font-bold">Nord Equipement Fermetures</span> est en mesure de vous proposer un grand choix de clôtures souples ou rigides, en adéquation avec le style de votre propriété.
                    </p>
                    <p class="text-gray-500">
                        Nous vous offrons un vaste assortiment de portes sectionnelles haut de gamme et de produits innovateurs en acier et en aluminium, avec ou sans fenêtres, dans pratiquement <span class="text-curr-black font-bold">toutes les dimensions et tous les coloris</span>. Grâce aux nombreuses combinaisons possibles, les portes s’intègrent facilement dans <span class="text-curr-black font-bold">tout bâtiment industriel ou commercial</span>. Leur commande est aisée, elles sont fonctionnelles et elles embellissent votre façade.
                    </p>
                </div>
            </section>
            <section class="pb-20">
                <h4 class="text-4xl font-bold pb-16">Nos travaux</h4>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div v-for="i in data?.servicePageCollection?.items[0]?.catalogCollection?.items" class="object-cover">
                        <img class="rounded-lg aspect-square object-cover" :src="i.url" alt="image">
                    </div>
                </div>
            </section>
        </div>

    </AppLayout>
</template>

<style scoped>

</style>
