<script setup>
import { ref, onMounted, nextTick } from 'vue'

const showAllFeatures = ref(false)

onMounted(async () => {
  if (import.meta.client) {
    const { default: WOW } = await import('wow.js')
    const wow = new WOW({
      boxClass: 'wow',
      animateClass: 'animate__animated',
      offset: 100,
      mobile: true,
      live: true
    })
    wow.init()
  }
})

const toggleFeatures = async () => {
  showAllFeatures.value = !showAllFeatures.value
  await nextTick()
  if (import.meta.client) {
    const { default: WOW } = await import('wow.js')
    new WOW({ animateClass: 'animate__animated', live: true }).init()
  }
}

// App Features tailored for Reading + Quiz + Performance tracking
const features = [
  {
    title: 'Immersive Story Mode',
    description: 'Read curated short stories and vocabulary rich chapters with instant dictionary and context help.',
    iconPath: 'M12 6.042A8.967 8.967 0 006 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 016 18c2.305 0 4.408.867 6 2.292m0-14.25a8.966 8.966 0 016-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0018 18a8.967 8.967 0 00-6 2.292m0-14.25v14.25'
  },
  {
    title: 'Interactive Quizzes',
    description: 'Test your comprehension immediately after reading each chapter with adaptive multiple-choice quizzes.',
    iconPath: 'M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M12 18h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z'
  },
  {
    title: 'Instant Scoring',
    description: 'Get immediate marks, detailed answer breakdowns, and explanation for every correct and incorrect answer.',
    iconPath: 'M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z'
  },
  {
    title: 'Deep Performance Analytics',
    description: 'Track overall reading speed, accuracy percentage, weak areas, and score trends with visual charts.',
    iconPath: 'M3 13.125C3 12.504 3.504 12 4.125 12h2.25c.621 0 1.125.504 1.125 1.125v6.75C7.5 20.496 6.996 21 6.375 21h-2.25A1.125 1.125 0 013 19.875v-6.75zM9.75 8.625c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v11.25c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V8.625zM16.5 4.125c0-.621.504-1.125 1.125-1.125h2.25C20.496 3 21 3.504 21 4.125v15.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 01-1.125-1.125V4.125z'
  },
  {
    title: 'Daily Streak & Badges',
    description: 'Build daily reading habits, unlock milestone achievements, and stay motivated with gamified learning.',
    iconPath: 'M15.362 5.214A8.252 8.252 0 0112 21 8.25 8.25 0 016.038 7.048 8.287 8.287 0 009 9.6a8.983 8.983 0 013.361-6.867 8.21 8.21 0 003 2.48z'
  },
  {
    title: 'Personalized Recommendations',
    description: 'AI detects your reading difficulty preference and suggests stories tailored to boost your comprehension.',
    iconPath: 'M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09z'
  }
]

const valueProps = [
  { title: 'Read & Retain', desc: 'Active reading combined with quizzes ensures 3x better retention.', icon: 'M12 6.042A8.967 8.967 0 006 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 016 18c2.305 0 4.408.867 6 2.292m0-14.25a8.966 8.966 0 016-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0018 18a8.967 8.967 0 00-6 2.292m0-14.25v14.25' },
  { title: 'Real-Time Marks', desc: 'Know your score instantly with automated AI evaluation.', icon: 'M16.5 18.75h-9m9-3h-9m9-3h-9m9-3h-9m12-3h-15' },
  { title: 'Weak Spot Detector', desc: 'Identify specific topics or words you consistently get wrong.', icon: 'M10.5 6a7.5 7.5 0 107.5 7.5h-7.5V6z' },
  { title: 'Cross-Platform Sync', desc: 'Practice anywhere on iOS, Android, or Web seamlessly.', icon: 'M10.5 1.5H8.25A2.25 2.25 0 006 3.75v16.5a2.25 2.25 0 002.25 2.25h7.5A2.25 2.25 0 0018 20.25V3.75a2.25 2.25 0 00-2.25-2.25H13.5m-3 0V3h3V1.5m-3 0h3' }
]

const plans = [
  { name: 'Learner', price: '$0.00', desc: 'Start reading stories and taking basic quizzes for free.', features: ['5 Stories / Month', 'Standard Quizzes', 'Basic Score Summary', 'Community Leaderboard'], highlight: false },
  { name: 'Pro Scholar', price: '$4.99', desc: 'Full access to all stories, unlimited quizzes, and analytics.', features: ['Unlimited Stories & Content', 'Adaptive Dynamic Quizzes', 'Advanced Performance Analytics', 'Custom Weak Spot Drills', 'Offline Reading Mode'], highlight: true },
  { name: 'Team / School', price: '$12.99', desc: 'Ideal for classrooms, language centers, and study groups.', features: ['All Pro Scholar Features', 'Teacher & Student Dashboard', 'Custom Quiz Builder', 'Bulk Performance Reports', 'Dedicated Support'], highlight: false }
]
</script>

<template>
  <div
    class="min-h-screen bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300">

    <!-- HERO SECTION -->
    <section
      class="relative py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <div class="wow animate__animated animate__fadeInLeft space-y-6 text-center lg:text-left">
        <div
          class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full border border-slate-950/20 dark:border-white/20 bg-paper-light-badge dark:bg-paper-dark-badge text-xs font-bold text-slate-900 dark:text-amber-300 shadow-xs">
          <span>📚 Interactive Story & Quiz App</span>
        </div>
        <h1
          class="text-4xl sm:text-6xl font-serif font-bold tracking-tight text-slate-950 dark:text-amber-50 leading-tight">
          Read Content, Take Quizzes & Master Knowledge with <br />
          <span class="text-paper-accent dark:text-paper-accent-dark">SobdoGolpo App</span>
        </h1>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 max-w-xl mx-auto lg:mx-0 font-sans">
          SobdoGolpo turns regular reading into an interactive learning experience. Read engaging stories, test your
          recall with instant quizzes, and track your performance growth with real-time analytics.
        </p>
        <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4">
          <button
            class="px-8 py-3.5 rounded-2xl border-2 border-slate-950 dark:border-amber-300/40 bg-slate-950 text-white dark:bg-paper-accent-dark dark:text-slate-950 font-bold hover:scale-105 transition-all shadow-md">
            Start Reading Free
          </button>
          <button
            class="px-8 py-3.5 rounded-2xl border-2 border-slate-950/20 dark:border-white/20 bg-paper-light-card dark:bg-paper-dark-card text-slate-950 dark:text-slate-100 font-bold hover:scale-105 transition-all">
            Try Demo Quiz
          </button>
        </div>
      </div>

      <!-- Hero Visual: Mock App UI showing Reading + Quiz + Score -->
      <div class="wow animate__animated animate__fadeInRight relative flex justify-center">
        <div
          class="w-full max-w-md p-6 rounded-[2.5rem] border-2 border-slate-950/20 dark:border-white/20 bg-paper-light-card dark:bg-paper-dark-card shadow-2xl hover:scale-105 transition-transform duration-300">
          <div
            class="p-6 rounded-[1.5rem] border border-slate-950/15 dark:border-white/15 bg-paper-light/80 dark:bg-paper-dark-preview space-y-4">
            <!-- Story Header -->
            <div class="flex items-center justify-between border-b border-slate-950/10 dark:border-white/10 pb-3">
              <div>
                <span
                  class="text-xs text-amber-600 dark:text-amber-400 font-bold uppercase tracking-wider block">Chapter
                  3</span>
                <span class="font-serif font-bold text-base text-slate-950 dark:text-slate-50">The Lost City
                  Story</span>
              </div>
              <span
                class="text-xs bg-emerald-500/20 text-emerald-700 dark:text-emerald-300 px-2.5 py-1 rounded-full font-bold">Quiz
                Ready</span>
            </div>

            <!-- Quiz Question Card preview -->
            <div class="p-4 rounded-xl bg-slate-900/5 dark:bg-slate-800/40 space-y-3">
              <p class="text-xs font-bold text-slate-900 dark:text-amber-100">Q: What was the main motive of the
                explorer in Chapter 3?</p>
              <div class="space-y-1.5 text-xs">
                <div
                  class="p-2 rounded-lg bg-emerald-500/20 text-emerald-800 dark:text-emerald-200 flex justify-between items-center border border-emerald-500/40 font-semibold">
                  <span>✓ Decipher the ancient scroll</span>
                  <span class="text-[10px] bg-emerald-600 text-white px-1.5 py-0.5 rounded">+10 pts</span>
                </div>
                <div class="p-2 rounded-lg bg-slate-200/60 dark:bg-slate-700/50 text-slate-600 dark:text-slate-400">
                  <span>Finding hidden treasure</span>
                </div>
              </div>
            </div>

            <!-- Performance Card preview -->
            <div
              class="pt-2 flex justify-between items-center text-xs font-bold border-t border-slate-950/10 dark:border-white/10">
              <div class="flex items-center gap-1.5 text-emerald-600 dark:text-emerald-400">
                <span>Score: 92%</span>
              </div>
              <div class="text-amber-600 dark:text-amber-300">
                <span>Streak: 🔥 5 Days</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- AMAZING FEATURES SECTION -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div class="wow animate__animated animate__fadeInUp text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Features Built for Smart Readers
        </h2>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
          SobdoGolpo seamlessly combines storytelling with interactive learning and performance analysis.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 items-stretch">
        <template v-for="(item, index) in features" :key="index">
          <div v-if="index < 3 || showAllFeatures"
            class="wow animate__animated animate__fadeInUp group relative p-8 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card shadow-md hover:shadow-2xl hover:scale-105 hover:z-30 transition-all duration-300 flex flex-col justify-between"
            :data-wow-delay="`${(index % 3) * 0.2}s`">
            <div>
              <div
                class="size-14 rounded-full border border-slate-950/20 dark:border-white/20 bg-paper-light-badge dark:bg-paper-dark-icon text-slate-950 dark:text-amber-300 flex items-center justify-center mb-6 shadow-xs">
                <svg class="size-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" :d="item.iconPath" />
                </svg>
              </div>
              <h3 class="text-2xl font-serif font-bold text-slate-950 dark:text-amber-50 mb-3">
                {{ item.title }}
              </h3>
              <p class="text-sm sm:text-base leading-relaxed text-slate-800 dark:text-slate-200 font-sans">
                {{ item.description }}
              </p>
            </div>
          </div>
        </template>
      </div>

      <div class="mt-16 text-center">
        <button @click="toggleFeatures" type="button"
          class="inline-flex items-center justify-center gap-x-2 rounded-2xl border-2 border-slate-950/30 dark:border-amber-300/40 bg-paper-light-card dark:bg-paper-dark-badge px-10 py-3.5 text-sm font-bold text-slate-950 dark:text-amber-200 shadow-md transition-all duration-200 hover:bg-slate-200 dark:hover:bg-paper-dark-icon hover:scale-105 cursor-pointer">
          <span>{{ showAllFeatures ? 'Show Less Features' : 'Learn More Features' }}</span>
          <svg class="size-4 transition-transform duration-200" :class="showAllFeatures ? 'rotate-180' : ''" fill="none"
            stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
          </svg>
        </button>
      </div>
    </section>

    <!-- WHY CHOOSE SECTION -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div class="wow animate__animated animate__fadeIn text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Why Practice with SobdoGolpo?
        </h2>
        <p class="text-base text-slate-800 dark:text-slate-200 font-sans">Engineered for students, language learners,
          and
          avid readers who want measurable progress.</p>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div v-for="(vp, idx) in valueProps" :key="idx"
          class="wow animate__animated animate__zoomIn p-6 rounded-[2rem] border border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card text-center space-y-3 hover:scale-105 transition-transform shadow-xs"
          :data-wow-delay="`${idx * 0.15}s`">
          <div
            class="size-12 mx-auto rounded-full bg-paper-light-badge dark:bg-paper-dark-icon text-slate-950 dark:text-amber-300 flex items-center justify-center">
            <svg class="size-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" :d="vp.icon" />
            </svg>
          </div>
          <h4 class="font-serif font-bold text-lg text-slate-950 dark:text-amber-50">{{ vp.title }}</h4>
          <p class="text-xs leading-relaxed text-slate-800 dark:text-slate-200">{{ vp.desc }}</p>
        </div>
      </div>
    </section>

    <!-- PRICING SECTION -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div class="wow animate__animated animate__fadeInUp text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Flexible Learning Plans
        </h2>
        <p class="text-base text-slate-800 dark:text-slate-200 font-sans">Choose the plan that fits your learning pace
          and
          targets.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-stretch">
        <div v-for="(plan, idx) in plans" :key="idx"
          class="wow animate__animated animate__fadeInUp p-8 rounded-[2rem] bg-paper-light-card dark:bg-paper-dark-card flex flex-col justify-between shadow-lg hover:scale-105 transition-transform"
          :class="plan.highlight ? 'border-amber-600 dark:border-amber-400 border-4 scale-105' : 'border-2 border-slate-950/15 dark:border-white/15'"
          :data-wow-delay="`${idx * 0.2}s`">
          <div class="space-y-4">
            <h3 class="text-2xl font-serif font-bold text-slate-950 dark:text-amber-50">{{ plan.name }}</h3>
            <div class="text-4xl font-serif font-bold text-paper-accent dark:text-paper-accent-dark">
              {{ plan.price }}<span class="text-xs font-sans text-slate-700 dark:text-slate-300">/month</span>
            </div>
            <p class="text-xs text-slate-800 dark:text-slate-200 font-sans">{{ plan.desc }}</p>
            <ul class="space-y-2 pt-4 border-t border-slate-950/10 dark:border-white/10 font-sans text-xs">
              <li v-for="(f, i) in plan.features" :key="i"
                class="flex items-center gap-2 text-slate-800 dark:text-slate-200">
                <span class="text-emerald-700 dark:text-emerald-400 font-bold">✓</span> {{ f }}
              </li>
            </ul>
          </div>
          <button
            class="mt-8 w-full py-3 rounded-xl border-2 border-slate-950 dark:border-amber-300/40 bg-slate-950 text-white dark:bg-paper-dark-badge dark:text-amber-200 font-bold text-xs hover:scale-105 transition-transform">
            Choose Plan
          </button>
        </div>
      </div>
    </section>

    <!-- FOOTER CALLOUT BANNER -->
    <section class="py-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div
        class="wow animate__animated animate__zoomIn p-10 rounded-[2.5rem] bg-slate-950 dark:bg-paper-dark-card border-2 border-slate-950 dark:border-amber-300/30 text-center space-y-6 shadow-2xl">
        <h2 class="text-3xl sm:text-4xl font-serif font-bold text-amber-100">Ready to Elevate Your Reading & Retention?
        </h2>
        <p class="text-sm text-slate-200 max-w-xl mx-auto font-sans">Download SobdoGolpo today, dive into stories,
          attempt
          instant quizzes, and watch your performance score rise.</p>
        <button
          class="px-10 py-3.5 rounded-2xl bg-paper-light-badge dark:bg-paper-accent-dark text-slate-950 font-bold hover:scale-105 transition-transform text-sm shadow-md">
          Download SobdoGolpo Free
        </button>
      </div>
    </section>

  </div>
</template>