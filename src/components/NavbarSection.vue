<script setup lang="ts">
    import { onMounted } from 'vue';

    onMounted(() => {
        const hamburger = document.querySelector("#hamburger");
        if (hamburger) {
            hamburger.addEventListener("click", function() {
                hamburger.classList.toggle("hamburger-active");
            });
        }
    });
</script>

<style>
    .hamburger-line {
        @apply w-8 h-1 my-2 block bg-stone-700 transition duration-300;
    }

    .hamburger-active > span:nth-child(1) {
        @apply rotate-[55deg];
    }

    .hamburger-active > span:nth-child(2) {
        @apply bg-transparent;
    }

    .hamburger-active > span:nth-child(3) {
        @apply -rotate-[55deg];
    }
</style>
<template>
    <div class="fixed top-0 left-0 right-0 px-5 py-3 flex justify-between">
        <logoSection class="text-5xl font-semibold text-stone-700 mulish">;</logoSection>
        <div class="my-2 mx-1 flex items-center">
            <button id="hamburger" type="button" >
                <span class="hamburger-line origin-top-left"></span>
                <span class="hamburger-line"></span>
                <span class="hamburger-line origin-bottom-left"></span>
            </button>
        </div>
    </div>
</template>