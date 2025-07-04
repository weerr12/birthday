<script setup lang="ts">
import { ref, onMounted } from 'vue'

const showAnimation = ref(false)

onMounted(() => {
  setTimeout(() => {
    showAnimation.value = true
  }, 500)
})
</script>

<template>
  <div
    class="min-h-screen bg-gradient-to-br from-rose-100 via-pink-100 to-indigo-100 relative overflow-hidden"
  >
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute top-10 left-10 text-4xl animate-bounce opacity-70">🎈</div>
      <div class="absolute top-20 right-20 text-3xl animate-pulse opacity-70">🎊</div>
      <div class="absolute bottom-20 left-20 text-5xl animate-spin opacity-70" style="animation-duration: 8s;">🎉</div>
      <div class="absolute bottom-10 right-10 text-4xl animate-bounce opacity-70" style="animation-delay: 1s;">🎁</div>
      <div class="absolute top-1/2 left-5 text-3xl animate-pulse opacity-50" style="animation-delay: 2s;">⭐</div>
      <div class="absolute top-1/3 right-5 text-3xl animate-bounce opacity-50" style="animation-delay: 1.5s;">🌟</div>
      
      <div v-if="showAnimation" class="absolute inset-0">
        <div v-for="i in 20" :key="'confetti-' + i"
             class="absolute w-2 h-2 rounded-full animate-ping"
             :class="['bg-pink-400', 'bg-purple-400', 'bg-yellow-400', 'bg-blue-400', 'bg-green-400'][Math.floor(Math.random() * 5)]"
             :style="{
               left: Math.random() * 100 + '%',
               top: Math.random() * 100 + '%',
               animationDelay: Math.random() * 3 + 's',
               animationDuration: '2s'
             }"></div>
      </div>
    </div>

    <div class="relative z-10">
      <div class="flex justify-center items-center min-h-screen px-4 py-8">
        <div class="bg-white/80 backdrop-blur-sm rounded-2xl shadow-2xl p-6 sm:p-8 max-w-sm sm:max-w-md lg:max-w-lg w-full transform hover:scale-105 transition-all duration-300">
          <div class="text-center mb-6">
            <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold bg-gradient-to-r from-pink-500 via-purple-500 to-indigo-500 bg-clip-text text-transparent mb-2 animate-pulse">
              Happy Birthday!
            </h1>
            <div class="text-2xl sm:text-3xl mb-4">🎂✨</div>
          </div>

          <div class="text-center mb-6">
            <p class="text-gray-700 text-sm sm:text-base lg:text-lg leading-relaxed mb-4 font-medium">
              22 แล้วนะ ขอให้ปีนี้มีแต่เรื่องดีๆ รักตัวเองเยอะๆ กินเหล้ากันเพื่อน 555555
            </p>
          </div>
          <div>
            <img src="/beam.jpg" alt="beam" class="rounded-lg shadow-lg w-full h-auto mb-6">
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-3 gap-3 sm:gap-4 mb-6">
            <div class="bg-gradient-to-br from-pink-100 to-pink-200 rounded-xl p-3 sm:p-4 text-center transform hover:scale-105 transition-all duration-300 shadow-md">
              <div class="text-2xl sm:text-3xl mb-2">💝</div>
              <p class="text-pink-700 font-semibold text-xs sm:text-sm">ความสุข</p>
            </div>
            <div class="bg-gradient-to-br from-purple-100 to-purple-200 rounded-xl p-3 sm:p-4 text-center transform hover:scale-105 transition-all duration-300 shadow-md">
              <div class="text-2xl sm:text-3xl mb-2">🌟</div>
              <p class="text-purple-700 font-semibold text-xs sm:text-sm">โชคดี</p>
            </div>
            <div class="bg-gradient-to-br from-blue-100 to-blue-200 rounded-xl p-3 sm:p-4 text-center transform hover:scale-105 transition-all duration-300 shadow-md">
              <div class="text-2xl sm:text-3xl mb-2">🎁</div>
              <p class="text-blue-700 font-semibold text-xs sm:text-sm">สมหวัง</p>
            </div>
          </div>

          <div class="flex justify-center mt-6 space-x-2">
            <span class="text-2xl sm:text-3xl animate-bounce" style="animation-delay: 0.1s">🎈</span>
            <span class="text-2xl sm:text-3xl animate-bounce" style="animation-delay: 0.2s">🎊</span>
            <span class="text-2xl sm:text-3xl animate-bounce" style="animation-delay: 0.3s">🎉</span>
            <span class="text-2xl sm:text-3xl animate-bounce" style="animation-delay: 0.4s">🎁</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
