<template>
    <section class="relative h-screen overflow-hidden bg-gradient-to-br from-blue-900 via-gray-900 to-black">
        <div class="container mx-auto px-6 py-48">
            <div class="grid lg:grid-cols-2 gap- items-center justify-between">
                <div>
                    <p class="text-sm text-gray-400 mb-4">CREATED BY ENVATO CREATIVE HEROES</p>
                    <h1 class="text-5xl lg:text-7xl font-bold mb-6 leading-tight">
                        Web Agency<br>
                        WordPress Theme
                    </h1>
                    <div class="flex flex-wrap gap-4 mb-12">
                        <button class="bg-blue-600 hover:bg-blue-700 px-6 py-3 transition-colors">
                            Pre-Build Demos
                            <Icon name="lucide:arrow-up-right" class="w-4 h-4 ml-2 inline" />
                        </button>
                        <button class="bg-blue-600 hover:bg-blue-700 px-6 py-3 transition-colors">
                            Online Documentation
                            <Icon name="lucide:arrow-up-right" class="w-4 h-4 ml-2 inline" />
                        </button>
                    </div>
                    <div class="grid grid-cols-3 gap-8 pt-20">
                        <div>
                            <div class="text-6xl font-bold">24+</div>
                            <div class="text-gray-200 text-xl">Dark & Light Demo</div>
                        </div>
                        <div>
                            <div class="text-6xl font-bold">30+</div>
                            <div class="text-gray-200 text-xl">Dark & Light Inner Pages</div>
                        </div>
                        <div>
                            <div class="text-6xl font-bold">72+</div>
                            <div class="text-gray-200 text-xl">Section Elements</div>
                        </div>
                    </div>
                </div>
                <div class="relative h-full">
                    <div class="flex justify-center items-center h-full">
                        <!-- Small banner in the center-left -->
                        <div class="relative transform -translate-x-1/2 translate-y-1/2">
                            <img src="/banner-small.png" alt="Device Mockups" class="w-full h-auto" />
                        </div>
                        <!-- Big banner on the right side, partially hidden -->
                        <div class="absolute right-0 transform translate-x-1/2">
                            <img src="/banner-big.png" alt="Device Mockups" class="w-full h-auto " />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
// Banner component script
</script>

<style scoped>
/* Banner component styles */



</style>
