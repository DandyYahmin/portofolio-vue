<script setup lang="ts">
    import {ref, onMounted} from 'vue'

    const props = defineProps<({
        time: number | null
        backgroundColor: string | null,
        loaderColor: string | null
    })>()
    
    const isVisible = ref(false)
    const showLoad = () => {
        isVisible.value = true 
        setTimeout(() => {
            isVisible.value = false;
        }, props.time ?? 10000)
    }

    onMounted(() => {
        showLoad()
    })
</script>

<template>
    <div v-if="isVisible" :style="{backgroundColor: backgroundColor || 'white'}" 
    class="flex justify-center items-center fixed top-0 left-0 w-full h-full z-[99]">
        <div :style="{borderColor: backgroundColor || 'white',
            borderTopColor: loaderColor || 'black',
            borderRightColor: loaderColor || 'black'
        }" 
        class="w-20 h-20 m-2 border-4 rounded-full animate-spin"></div>
    </div>
</template>