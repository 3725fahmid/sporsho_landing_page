<script setup>
import { ref } from 'vue'

const showAll = ref(false)

const features = [
  {
    title: 'Daily Habit Tracker',
    description: 'Track your wellness activities and productivity goals with our interactive habit tracker, keeping you on top of your progress.',
    iconPath: 'M12 18v-5.25m0 0a6.01 6.01 0 001.5-.189m-1.5.189a6.01 6.01 0 01-1.5-.189m3.75 7.478a12.06 12.06 0 01-4.5 0m3.75 2.383a14.406 14.406 0 01-3 0M14.25 18v-.192c0-.983.658-1.823 1.508-2.316a7.5 7.5 0 10-7.517 0c.85.493 1.509 1.333 1.509 2.316V18'
  },
  {
    title: 'Engagement Support',
    description: 'Connect with like-minded individuals who are focused on enhancing both their wellness and productivity.',
    iconPath: 'M18 18.72a9.094 9.094 0 003.741-.479 3 3 0 00-4.682-2.72m.94 3.198l.001.031c0 .225-.012.447-.037.666A11.944 11.944 0 0112 21c-2.17 0-4.207-.576-5.963-1.584A6.062 6.062 0 016 18.719m12 0a5.971 5.971 0 00-.941-3.197m0 0A5.995 5.995 0 0012 12.75a5.995 5.995 0 00-5.058 2.772m0 0a5.97 5.97 0 00-.942 3.197M15 6.75a3 3 0 11-6 0 3 3 0 016 0zm6 3a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0zm-13.5 0a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0z'
  },
  {
    title: 'The Wellness Resource',
    description: 'Help your employees on their wellness journey with personalized, actionable guidance.',
    iconPath: 'M11.35 3.836c-.065.21-.1.433-.1.664 0 .414.336.75.75.75h4.5a.75.75 0 00.75-.75 2.25 2.25 0 00-.1-.664m-5.8 0A2.251 2.251 0 0113.5 2.25h1.5c.53 0 1.01.184 1.39.493m-5.8 0c-.38.309-.664.736-.803 1.228m7.406 0c.139.492.115 1.019-.069 1.493M12 10.5h.008v.008H12V10.5zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z'
  },
  {
    title: 'Reporting and Analytics',
    description: 'Get insights into health metrics with powerful analytics tools made for team performance.',
    iconPath: 'M2.25 18L9 11.25l4.306 4.307a11.95 11.95 0 005.814-5.519l2.74-1.22m0 0l-5.94-2.28 2.2 5.92m3.74-3.64l-1.22 2.74a11.959 11.959 0 01-5.518 5.814L11.25 13.5 4.5 20.25'
  },
  {
    title: 'AI Wellness Integrate Tools',
    description: 'Enhance and personalize health solutions easily through tailored AI integrations.',
    iconPath: 'M9.75 3.104v5.714a2.25 2.25 0 01-.659 1.591L5 14.5M9.75 3.104c-.251.023-.501.05-.75.082m.75-.082a24.301 24.301 0 014.5 0m0 0v5.714c0 .597.237 1.17.659 1.591L19 14.5'
  }
]
</script>

<template>
  <section class="relative py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
    <!-- Section Header -->
    <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
      <h2 class="text-3xl sm:text-5xl font-bold text-slate-900 dark:text-amber-50/90 tracking-tight">
        Unlock Our Fantastic Features!
      </h2>
      <p class="text-base sm:text-lg text-slate-600 dark:text-emerald-100/60 max-w-2xl mx-auto font-sans">
        Explore our dynamic and effective tools that make enhancing your wellness and productivity effortless and
        enjoyable!
      </p>
    </div>

    <!-- Paper Cards Grid -->
    <div class="relative grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 items-stretch">
      <template v-for="(item, index) in features" :key="index">
        <!-- Render card if index < 3 OR if showAll is true -->
        <div v-if="index < 3 || showAll"
          class="group relative p-8 rounded-[2rem] border-2 border-slate-900/10 dark:border-white/10 bg-[#fdfaf3] dark:bg-[#111c17] text-slate-900 dark:text-slate-100 shadow-md hover:shadow-2xl hover:scale-105 hover:z-30 transition-all duration-300 flex flex-col justify-between">
          <div>
            <div
              class="size-14 rounded-full border border-slate-900/20 dark:border-white/20 bg-[#f3e3a9] dark:bg-[#25382e] text-slate-900 dark:text-amber-200 flex items-center justify-center mb-6 shadow-xs">
              <svg class="size-6" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" :d="item.iconPath" />
              </svg>
            </div>
            <h3 class="text-2xl font-serif font-bold text-slate-900 dark:text-amber-50 mb-3">
              {{ item.title }}
            </h3>
            <p class="text-sm sm:text-base leading-relaxed text-slate-700 dark:text-slate-300 font-sans">
              {{ item.description }}
            </p>
          </div>
        </div>
      </template>
    </div>

    <!-- Center Toggle Button -->
    <div class="mt-16 text-center">
      <button @click="showAll = !showAll" type="button"
        class="inline-flex items-center justify-center gap-x-2 rounded-2xl border-2 border-slate-900 dark:border-amber-100/30 bg-[#faf6ed] dark:bg-[#1d2b25] px-10 py-3.5 text-sm font-bold text-slate-900 dark:text-amber-100 shadow-md transition-all duration-200 hover:bg-slate-200 dark:hover:bg-[#283b33] hover:scale-105 cursor-pointer">
        <span>{{ showAll ? 'Show Less' : 'Learn More' }}</span>
        <svg class="size-4 transition-transform duration-200" :class="showAll ? 'rotate-180' : ''" fill="none"
          stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
        </svg>
      </button>
    </div>
  </section>
</template>