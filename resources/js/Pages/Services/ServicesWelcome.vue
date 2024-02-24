<script setup>
import AppLayout from "@/Layouts/AppLayout.vue";
import {onMounted, onUnmounted, ref} from "vue";
import {useContentfulFetch} from "@/Composable/fetchContentfullApi.js";

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
    <AppLayout v-if="data">
        <div class="md:pt-20 md:px-20 p-8">
            <h1 class="text-3xl font-bold pb-16">Découvrer nos différents services</h1>

            <div class="grid sm:grid-cols-2 gap-8">
                <div class="bg-gray-200 shadow-xl text-center rounded-xl text-curr">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[0]?.url" class="w-full h-48 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8">
                        <h1 class="font-bold text-xl pb-2 text-gray-900">Portes Sectionales</h1>
                        <p>Nos portes sectionales sont conçues pour offrir une sécurité optimale tout en assurant une isolation thermique efficace. Fabriquées avec des panneaux isolés d'une épaisseur de 40 mm, elles sont équipées de rails de guidage en acier galvanisé, de galets nylon sur roulement à billes et d'une quincaillerie en acier laqué blanc. Les options disponibles incluent un portillon de service, une serrure ou un verrou en option, un système de sécurité électrique et un moteur 24 volts.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl text-center rounded-xl text-curr">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[1]?.url" class="w-full h-48 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8">
                        <h1 class="font-bold text-xl pb-2 text-gray-900">Portes à Déplacement Latéral</h1>
                        <p>
                            Nos portes à déplacement latéral offrent une solution pratique pour les espaces restreints. Avec des panneaux isolés d'une épaisseur de 40 mm, elles sont équipées de rails de guidage en aluminium, de galets nylon sur roulement à billes et d'une quincaillerie en acier laqué blanc. Les options comprennent un portillon de service, une serrure deux points avec poignée inox extérieure, un système de sécurité électrique et un moteur 24 volts.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl text-center rounded-xl text-curr">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[2]?.url" class="w-full h-48 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8">
                        <h1 class="font-bold text-xl pb-2 text-gray-900">Portails Industriels</h1>
                        <p>
                            Nos portails industriels sont conçus pour offrir une sécurité maximale tout en s'intégrant parfaitement à votre environnement. Disponibles en version autoportée automatique ou en aluminium de type contemporain ou traditionnel, nos portails sont fabriqués avec des matériaux de haute qualité pour assurer une durabilité et une fiabilité exceptionnelles.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-200 shadow-xl text-center rounded-xl text-curr">
                    <img :src="data?.servicePageCollection?.items[0]?.cardImgCollection?.items[3]?.url" class="w-full h-48 object-cover rounded-t-xl" alt="image" />
                    <div class="p-8">
                        <h1 class="font-bold text-xl pb-2 text-gray-900">Options Diverses</h1>
                        <p>
                            Nous proposons également une gamme d'options pour personnaliser vos équipements de fermeture, y compris des boîtes à clés, des visiophones, une ouverture par smartphone et des claviers à codes.
                        </p>
                    </div>
                </div>
            </div>

            <section class="py-24">
                <div class="py-24 text-center">
                    <h4 class="text-2xl font-bold pb-4">Contactez-nous pour une consultation personnalisée :</h4>
                    <p class="mb-3 text-gray-500">
                        Pour répondre au mieux à vos besoins spécifiques, nous vous encourageons à nous contacter directement. Que vous ayez une question, que vous souhaitiez obtenir des conseils ou que vous ayez besoin d'un devis personnalisé, notre équipe est là pour vous aider. Nous nous engageons à répondre efficacement et rapidement à toutes vos demandes, garantissant ainsi votre satisfaction.
                    </p>
                    <p class="mb-3 text-gray-500">
                        N'hésitez pas à nous contacter dès aujourd'hui pour découvrir comment nos portes sectionales peuvent répondre à vos besoins en matière de fermeture.
                    </p>
                </div>
            </section>
            <section class="pb-20">
                <h4 class="text-4xl font-bold pb-16">Nos travaux</h4>
                <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
                    <div v-for="i in data?.servicePageCollection?.items[0]?.catalogCollection?.items" class="object-cover">
                        <img class="h-auto max-w-full rounded-lg h-full object-cover" :src="i.url" alt="image">
                    </div>
                </div>
            </section>
        </div>

    </AppLayout>
</template>

<style scoped>

</style>
