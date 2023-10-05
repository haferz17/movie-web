<script>
import Header from '@/components/Header.vue'

export default {
    components: {
        Header
    }
}
</script>

<template>
    <div class="w-screen h-screen relative">
        <Header/>
        <div id="main" class="flex w-full overflow-scroll">
            <slot></slot>
        </div>
    </div>
</template>