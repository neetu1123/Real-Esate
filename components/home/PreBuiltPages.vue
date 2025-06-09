<template>
    <section class="py-20 bg-gradient-to-r from-blue-600 to-purple-600">
        <div class="">
            <div class="text-center mb-16">
                <p class="text-blue-100 text-sm mb-4">Build With Incredible</p>
                <h2 class="text-4xl lg:text-5xl font-bold mb-8">Pre-Built Inner Pages Ready</h2>
            </div>

            <div class="relative overflow-hidden mb-6">
                <div class="flex whitespace-nowrap animate-marquee space-x-6">
                    <div v-for="i in 12" :key="i"
                        class="inline-block flex-shrink-0 w-80 h-48 bg-gray-800 rounded-lg overflow-hidden">
                        <img :src="`/page-4.png`" :alt="`Page Template ${i}`" class="w-full h-full object-cover" />
                    </div>
                    <!-- Duplicate content for seamless loop -->
                    <div v-for="i in 12" :key="i + 12"
                        class="inline-block flex-shrink-0 w-80 h-48 bg-gray-800 rounded-lg overflow-hidden">
                        <img :src="`/page-4.png`" :alt="`Page Template ${i}`" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
            <!-- reverse direction -->
            <div class="relative overflow-hidden mt-6">
                <div class="flex whitespace-nowrap animate-marquee-reverse space-x-6">
                    <div v-for="i in 12" :key="i"
                        class="inline-block flex-shrink-0 w-80 h-48 bg-gray-800 rounded-lg overflow-hidden">
                        <img :src="`/page-4.png`" :alt="`Page Template ${i}`" class="w-full h-full object-cover" />
                    </div>
                    <!-- Duplicate content for seamless loop -->
                    <div v-for="i in 12" :key="i + 12"
                        class="inline-block flex-shrink-0 w-80 h-48 bg-gray-800 rounded-lg overflow-hidden">
                        <img :src="`/page-4.png`" :alt="`Page Template ${i}`" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
// PreBuiltPages component script
</script>

<style scoped>
@keyframes marquee {
    0% {
        transform: translateX(0%);
    }

    100% {
        transform: translateX(-100%);
    }
}

@keyframes marquee-reverse {
    0% {
        transform: translateX(-100%);
    }

    100% {
        transform: translateX(0%);
    }
}

.animate-marquee {
    animation: marquee 30s linear infinite;
    min-width: 100%;
}

.animate-marquee-reverse {
    animation: marquee-reverse 30s linear infinite;
    min-width: 100%;
}

/* Additional styles for better spacing */
.relative+.relative {
    margin-top: 2rem;
}
</style>
