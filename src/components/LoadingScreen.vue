<script setup lang="ts">
    import {ref, onMounted} from 'vue'

    const props = defineProps<({
        time: number | null
        backgroundColor: string | null,
        loaderColor: string | null,
        motivationText: boolean | null,
        loader: boolean | null
    })>()
    
    const isVisible = ref(false)
    const showLoad = () => {
        isVisible.value = true 
        setTimeout(() => {
            isVisible.value = false;
        }, props.time ?? 10000)
    }

    const texts = [
        "It's not failure that makes us afraid, but fear that makes us fail",
        "Life must be great, strong and everything",
        "Don't repeat the same mistakes, there are still many other mistakes that need to be tried",
        "Progress is not achieved by smart people who have no guts, progress is achieved by stupid people who are willing to do anything",
        "A program is never less than 90% complete, and never more than 95% complete",
        "Roses are red, violets are blue. Even though you are the worst, I still love you"
    ];
    const getRandomText = () => {
        return texts[Math.floor(Math.random() * texts.length)];
    };

    onMounted(() => {
        showLoad()
    })
</script>
<style>
    
</style>
<template>
    <div v-if="isVisible" :style="{backgroundColor: backgroundColor || 'white'}" 
    class="flex justify-center items-center fixed top-0 left-0 w-full h-full z-[99]">
        <div class="grid place-items-center gap-2">
            <img src="../assets/gifs/CodeIconsGray.gif" alt=""/>
            <p :style="{color: loaderColor || 'black'}" v-if="motivationText" 
            class="text-center roboto-mono underline underline-offset-4 mb-2 sm:w-1/2 text-decoration italic">"{{getRandomText()}}"</p>
            <div :style="{borderColor: loaderColor || 'white',
                borderTopColor: backgroundColor || 'black'
            }" 
            class="w-5 h-5 m-2 border-4 rounded-full animate-spin" v-if="loader"></div>
        </div>
    </div>
</template>