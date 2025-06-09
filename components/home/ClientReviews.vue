<template>
    <section class="py-20 bg-gray-900">
        <div class="">
            <div class="text-center mb-16">
                <p class="text-blue-400 text-sm mb-4">Build With Incredible</p>
                <h2 class="text-4xl lg:text-5xl font-bold">Good Clients Reviews</h2>
            </div>

            <div class="relative overflow-hidden">
                <div class="flex animate-marquee space-x-8">
                    <div v-for="review in reviews" :key="review.id"
                        class="flex-shrink-0 w-96 bg-gray-800 p-8 border border-gray-700">
                        <div class="flex items-start space-x-4 mb-6">
                            <Icon name="lucide:quote" class="w-8 h-8 text-gray-600 flex-shrink-0" />
                            <div>
                                <h4 class="font-bold text-lg">{{ review.name }}</h4>
                                <p class="text-blue-400 text-sm">{{ review.role }}</p>
                            </div>
                            <Icon name="lucide:quote" class="w-8 h-8 text-gray-600 flex-shrink-0 rotate-180" />
                        </div>
                        <p class="text-gray-300 italic">"{{ review.text }}"</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
const reviews = [
    {
        id: 1,
        name: 'falguniconnect',
        role: 'Customer Support',
        text: 'Theme is great, and support is even better, job well done.'
    },
    {
        id: 2,
        name: 'aaronburatti00',
        role: 'Customer Support',
        text: 'Really nice theme and excellent support from Sabbir Islam'
    },
    {
        id: 3,
        name: 'lukeduff00',
        role: 'Customer Support',
        text: 'A brilliant theme, also the support is incredible. Sabbir has been a huge help. Not only supporting me with theme issues but also general WP issues. i cant ask for more :)'
    },
    {
        id: 4,
        name: 'Saadi_Abdelm',
        role: 'Customer Support',
        text: 'Great theme with excellent customization options and outstanding support!'
    },
    {
        id: 1,
        name: 'falguniconnect',
        role: 'Customer Support',
        text: 'Theme is great, and support is even better, job well done.'
    },
    {
        id: 2,
        name: 'aaronburatti00',
        role: 'Customer Support',
        text: 'Really nice theme and excellent support from Sabbir Islam'
    },
    {
        id: 3,
        name: 'lukeduff00',
        role: 'Customer Support',
        text: 'A brilliant theme, also the support is incredible. Sabbir has been a huge help. Not only supporting me with theme issues but also general WP issues. i cant ask for more :)'
    },
    {
        id: 4,
        name: 'Saadi_Abdelm',
        role: 'Customer Support',
        text: 'Great theme with excellent customization options and outstanding support!'
    }
]
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

.animate-marquee {
    animation: marquee 25s linear infinite;
}
</style>
