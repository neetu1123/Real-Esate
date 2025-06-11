<template>
    <div ref="viewportContainer" class="h-screen bg-gray-100 flex items-center justify-center p-8">
        <div class="container mx-auto text-center">
            <button ref="hoverButton"
                class="px-6 py-3 bg-blue-600 text-white font-medium rounded-lg transition-all duration-300 transform hover:scale-105 focus:outline-none">
                Hover Effect
            </button>

            <div class="mt-6 text-gray-600">
                Hover over the button above to add an animated gradient border effect to the viewport
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: false
})
const hoverButton = ref<HTMLButtonElement | null>(null);
const viewportContainer = ref<HTMLDivElement | null>(null);

onMounted(() => {
    if (hoverButton.value && viewportContainer.value) {
        hoverButton.value.addEventListener('mouseenter', () => {
            viewportContainer.value?.classList.add('gradient-border');
        });

        hoverButton.value.addEventListener('mouseleave', () => {
            viewportContainer.value?.classList.remove('gradient-border');
        });
    }
});
</script>

<style>
@layer utilities {
    .gradient-border {
        position: relative;
        /* border-radius: 8px; */
        /* Add some border radius to the container */
        overflow: hidden;
        /* Ensure the border stays within the container's bounds */
    }

    .gradient-border::before {
        content: '';
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        border: 8px solid transparent;
        /* Slightly wider border for better visibility */
        background: linear-gradient(45deg, #f59e0b, #ef4444, #8b5cf6, #3b82f6, #10b981, #f59e0b) border-box;
        background-size: 300% 300%;
        -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
        mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
        -webkit-mask-composite: destination-out;
        mask-composite: exclude;
        pointer-events: none;
        animation: border-animation 3s ease infinite;
        z-index: 50;
    }

    @keyframes border-animation {
        0% {
            background-position: 0% 50%;
        }

        50% {
            background-position: 100% 50%;
        }

        100% {
            background-position: 0% 50%;
        }
    }
}
</style>