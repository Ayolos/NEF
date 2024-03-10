<template>
    <div class="relative flex items-center bg-gray-900 justify-center w-screen h-screen overflow-hidden rounded-b-xl bg-gray-200">
        <!-- Tache lumineuse -->
        <div class="absolute h-48 w-48 top-28 bg-curr blur-3xl z-40 rounded-full"></div>
        <div class="absolute h-48 w-48 bottom-48 left-48 bg-curr blur-3xl z-40 rounded-full"></div>
        <div class="absolute h-48 w-48 bottom-0 right-0 bg-curr blur-3xl z-40 rounded-full"></div>

        <!-- Contenu texte -->
        <div class="md:w-1/2 md:px-0 px-16 flex flex-col justify-center z-40">
            <div>
                <h1 class="text-curr font-bold sm:text-4xl text-2xl pb-6 rounded-md">
                    <slot name="title"></slot>
                </h1>
                <p class="sm:text-xl text-md text-gray-400 text-justify">
                    <slot name="subtitle"></slot>
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>

const props = defineProps({
    url: String
})

</script>

<style scoped>
.absolute {
    animation: scatter 3s ease-in-out infinite alternate;
}

@keyframes scatter {
    0% {
        box-shadow: 0 0 60px 5px rgba(255, 255, 255, 0.8);
    }
}

@function random($min, $max) {
    @return random($min) * ($max - $min) + $min;
}
</style>
