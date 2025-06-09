<template>
    <section class="py-20 bg-black">
        <div class="container mx-auto px-6">
            <div class="max-w-4xl mx-auto">
                <div class="text-center mb-16">
                    <h2 class="text-4xl lg:text-5xl font-bold mb-4">
                        FREQUENTLY<br>
                        ASKED QUESTIONS
                    </h2>
                    <p class="text-gray-400">ANSWERS TO COMMON QUERIES WE OFTEN RECEIVE</p>
                    <div class="flex justify-end mt-8">
                        <span class="bg-green-500 text-black px-4 py-2 rounded-full text-sm font-bold">GET TO KNOW
                            MORE</span>
                    </div>
                </div>

                <div class="space-y-4">
                    <div v-for="(faq, index) in faqs" :key="index" class="border-b border-gray-800">
                        <button @click="toggleFaq(index)"
                            class="w-full flex items-center justify-between py-6 text-left hover:text-blue-400 transition-colors">
                            <span class="text-lg font-medium">{{ faq.question }}</span>
                            <Icon :name="activeFaq === index ? 'lucide:minus' : 'lucide:plus'"
                                class="w-6 h-6 flex-shrink-0" />
                        </button>
                        <div v-if="activeFaq === index" class="pb-6">
                            <p class="text-gray-400 leading-relaxed">{{ faq.answer }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

const activeFaq = ref(0)

const faqs = [
    {
        question: 'WHAT INDUSTRIES DO YOU SPECIALIZE IN?',
        answer: 'I have experience working across various industries including but not limited to Technology, Healthcare, Fashion, Hospitality and Non Profit Organization.'
    },
    {
        question: 'WHAT IS YOUR TYPICAL PROJECT TIMELINE?',
        answer: 'Project timelines vary depending on scope and complexity. Typically, small projects take 2-4 weeks, medium projects 4-8 weeks, and large projects 8-16 weeks.'
    },
    {
        question: 'DO YOU OFFER POST-LAUNCH SUPPORT OR MAINTENANCE?',
        answer: 'Yes, we offer comprehensive post-launch support including bug fixes, updates, maintenance, and ongoing development support.'
    },
    {
        question: 'WHAT SOFTWARE AND TOOLS DO YOU USE FOR YOUR DESIGNS?',
        answer: 'We use industry-standard tools including Figma, Adobe Creative Suite, Sketch, and various prototyping tools to deliver high-quality designs.'
    },
    {
        question: 'DO YOUR DESIGNS ARE TAILORED TO EACH CLIENT?',
        answer: 'Every design is custom-tailored to meet your specific business needs, brand identity, and target audience requirements.'
    },
    {
        question: 'HOW DO I UPGRADE, DOWNGRADE, OR CANCEL?',
        answer: 'You can easily manage your subscription through your account dashboard. Contact our support team for assistance with any changes to your plan.'
    }
]

const toggleFaq = (index) => {
    activeFaq.value = activeFaq.value === index ? -1 : index
}
</script>

<style scoped>
/* FAQ component styles */
</style>
