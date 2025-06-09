<template>
  <div>
    <!-- Top bar - always fixed with gray background -->
    <div class="fixed top-0 left-0 right-0 z-20 bg-gray-800 text-white">
      <div class=" mx-auto px-6 py-3 flex items-center justify-between">
        <p>Neetu</p>
        <button class="px-4 py-1 bg-blue-600 hover:bg-blue-700 rounded transition-colors">Buy Now</button>
      </div>
    </div>

    <!-- Navigation bar - becomes sticky on scroll -->
    <header ref="header" :class="[
      'w-full z-20 transition-all duration-300',
      isScrolled ?
        'fixed top-10 left-0 right-0 bg-gradient-to-br from-blue-900 via-gray-900 to-black shadow-lg' :
        'absolute top-12 left-0 right-0 bg-transparent'
    ]">
      <nav class="container mx-auto px-6 py-4 flex items-center justify-between">
        <div class="flex items-center space-x-2">
          <div class="w-8 h-8 bg-blue-500 rounded-lg flex items-center justify-center">
            <Icon name="lucide:hexagon" class="!size-4 ml-2 " />
          </div>
          <span class="text-xl font-bold">RUNOK</span>
        </div>
        <div class="hidden md:flex items-center space-x-8">
          <a href="#" class="hover:text-blue-400 transition-colors">DEMO</a>
          <a href="#" class="hover:text-blue-400 transition-colors">INNER PAGES</a>
          <a href="#" class="hover:text-blue-400 transition-colors">FEATURES</a>
          <a href="#" class="hover:text-blue-400 transition-colors">TESTIMONIAL</a>
        </div>
        <button class="bg-blue-600 hover:bg-blue-700  text-white px-6 py-2 transition-colors">
          Purchase Now
          <Icon name="lucide:arrow-up-right" class="!size-4 ml-2 " />
        </button>
      </nav>
    </header>

    <!-- Spacer div for the combined height of both bars -->
    <div :style="{ height: combinedHeight + 'px' }"></div>
  </div>
</template>

<script setup lang="ts">

// State variables
const header = ref(null)
const headerHeight = ref(0)
const topBarHeight = ref(40) // Estimated height of the top bar
const isScrolled = ref(false)
const combinedHeight = computed(() => {
  return headerHeight.value + (isScrolled.value ? 0 : topBarHeight.value)
})

// Handle scroll events
const handleScroll = () => {
  const scrollTop = window.pageYOffset || document.documentElement.scrollTop
  const scrollThreshold = topBarHeight.value + 25 // Threshold slightly more than top bar height

  // Set isScrolled based on the scroll position
  isScrolled.value = scrollTop > scrollThreshold
}

// Lifecycle hooks
onMounted(() => {
  // Add scroll event listener
  window.addEventListener('scroll', handleScroll)

  // Calculate heights for the spacer
  nextTick(() => {
    // Get top bar height
    const topBar = document.querySelector('.fixed.top-10.bg-gray-900')
    if (topBar) {
      topBarHeight.value = topBar.offsetHeight
    }

    // Get header height
    if (header.value) {
      headerHeight.value = header.value.offsetHeight
    }
  })

  // Call once to set initial state
  handleScroll()
})

onUnmounted(() => {
  // Remove event listener when component is unmounted
  window.removeEventListener('scroll', handleScroll)
})
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
}

.animate-marquee-reverse {
  animation: marquee-reverse 25s linear infinite;
}
</style>