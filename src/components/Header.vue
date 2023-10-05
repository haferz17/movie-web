<script setup>
import { ref, onMounted } from 'vue'

const menu = ref([
    { id: 0, label: 'For You', active: true },
    { id: 1, label: 'Movie' },
    { id: 2, label: 'Series' }
])

onMounted(() => {
    var scrollTrigger = 100;
    
    window.onscroll = function() {
        // We add pageYOffset for compatibility with IE.
        if (window.scrollY >= scrollTrigger || window.pageYOffset >= scrollTrigger) {
            document.getElementById('header').classList.add('bg-black')
        } else {
            document.getElementById('header').classList.remove('bg-black')
        }
    }
})

</script>

<template>
    <div id="header" class="w-screen fixed z-10 top-0 right-0 flex duration-1000 items-center px-14 py-4">
        <p class="font-extrabold text-3xl">LOGO</p>

        <div class="flex gap-8 items-center pl-8">
            <p v-for="val in menu" :key="val.id" :class="`${ val.active ? 'text-white font-extrabold' : 'font-semibold'}`">{{ val.label }}</p>
        </div>
    </div>
</template>