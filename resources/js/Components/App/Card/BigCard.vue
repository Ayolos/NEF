<script setup>

</script>

<template>
    <div class="grid mb-8 border border-gray-200 rounded-lg shadow-sm dark:border-gray-700 md:mb-12 md:grid-cols-2 bg-white dark:bg-gray-800">
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 rounded-t-lg md:rounded-t-none md:rounded-ss-lg md:border-e dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Portes sectionnelles</h3>
                <slot name="section1"></slot>
                <p class="my-4 text-justify">Des portes de garage pratiques et isolantes, composées de panneaux isolés, idéales pour les entrepôts et les garages.</p>
            </blockquote>
        </figure>
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 md:rounded-se-lg dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Rideau Métallique</h3>
                <slot name="section2"></slot>
                <p class="my-4 text-justify">Des solutions de sécurité robustes pour les devantures de magasins et les entrepôts, fabriquées à partir de lames métalliques qui s'enroulent autour d'un axe. Le rideau métallique est la fermeture la plus utilisée pour sécuriser les accès. En plus d’être un retardateur d’effraction efficace et reconnu, il est un
                    élément extrêmement dissuasif.</p>
            </blockquote>
        </figure>
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 md:rounded-es-lg md:border-b-0 md:border-e dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Grille à Enroulement</h3>
                <slot name="section3"></slot>
                <p class="my-4 text-justify">Offrent une visibilité et une ventilation maximales tout en assurant la sécurité dans les centres commerciaux, les parkings et les espaces publics.</p>
            </blockquote>
        </figure>
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white border-gray-200 rounded-b-lg md:rounded-se-lg dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Porte Rapide</h3>
                <slot name="section4"></slot>
                <p class="my-4 text-justify">Des portes souples fabriquées à partir de matériaux comme le PVC, idéales pour les zones à fort trafic où la rapidité d'accès est essentielle. Avec les portes souples rapides, vous êtes sûrs d’avoir une solution sur-mesure par rapport à votre activité. Les portes rapides souples peuvent être
                    installées en intérieur ou en extérieur.</p>
            </blockquote>
        </figure>
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white border-t border-gray-200 rounded-t-none md:rounded-bl-lg md:border-e dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Niveleur de Quai</h3>
                <slot name="section5"></slot>
                <p class="my-4 text-justify">Facilitent le chargement et le déchargement des marchandises en compensant les différences de hauteur entre le quai et le véhicule de livraison.</p>
            </blockquote>
        </figure>
        <figure class="flex flex-col items-center justify-center p-8 text-center bg-white rounded-b-xl md:rounded-br-xl border-t border-gray-200 md:rounded-b-lg dark:bg-gray-800 dark:border-gray-700">
            <blockquote class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Sas d'Étanchéité</h3>
                <slot name="section6"></slot>
                <p class="my-4 text-justify">Installés autour des portes de quai pour empêcher les pertes d'énergie et les infiltrations d'air, de poussière ou d'eau lors du chargement ou du déchargement des marchandises.</p>
            </blockquote>
        </figure>
    </div>

</template>

<style scoped>

</style>
