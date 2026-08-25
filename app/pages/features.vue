<script setup>
import { onMounted } from 'vue'

onMounted(async () => {
  if (import.meta.client) {
    const { default: WOW } = await import('wow.js')
    new WOW({
      boxClass: 'wow',
      animateClass: 'animate__animated',
      offset: 100,
      mobile: true,
      live: true
    }).init()
  }
})

// Feature Breakdown Data
const coreValueProps = [
  {
    title: 'Interactive Reader & Sound Support',
    desc: 'Tap any complex word while reading to reveal instant child-friendly definitions, contextual usage, and native audio pronunciation.',
    icon: '🔊',
    tag: 'Reading Tech'
  },
  {
    title: 'Adaptive Comprehension Quizzes',
    desc: 'Quizzes adjust to individual reading speed and comprehension depth after every chapter, keeping learners challenged without feeling overwhelmed.',
    icon: '⚡',
    tag: 'Smart Assessment'
  },
  {
    title: 'Visual Progress & Marks Analytics',
    desc: 'Detailed performance breakdown highlighting accuracy, vocabulary retention, and areas needing extra practice over time.',
    icon: '📊',
    tag: 'Analytics'
  },
  {
    title: 'Gamified XP & Daily Streaks',
    desc: 'Earn rewards, unlock new story genres, and maintain reading streaks to transform study time into a fun habit.',
    icon: '🏆',
    tag: 'Gamification'
  },
  {
    title: 'Bilingual Story Library',
    desc: 'Rich collection of classic folktales, modern science stories, and history books available in both English and Bengali.',
    icon: '📚',
    tag: 'Curriculum'
  },
  {
    title: 'Offline Reading & Download Support',
    desc: 'Download story packages and quizzes to keep learning seamlessly during travel or without an active internet connection.',
    icon: '📲',
    tag: 'Accessibility'
  }
]

// How Learning Happens (3 Steps)
const learningPillars = [
  {
    number: '01',
    title: 'Discover & Read',
    desc: 'Learners pick stories aligned with their reading tier. Guided visual layout and tap-to-translate tools build active reading confidence.'
  },
  {
    number: '02',
    title: 'Test & Reinforce',
    desc: 'Immediate chapter quizzes test understanding. Instant feedback corrects misunderstandings right while the context is fresh.'
  },
  {
    number: '03',
    title: 'Master & Retain',
    desc: 'Spaced repetition modules revisit saved target vocabulary through quick micro-games so learned words stay in long-term memory.'
  }
]

// What Learners Receive
const inclusions = [
  'Unlimited access to 500+ leveled stories',
  'Instant vocabulary lookup with native pronunciation',
  'Chapter-end quizzes with instant score breakdowns',
  'Parent and educator progress dashboard',
  'Offline mode for learning anywhere',
  'Weekly new content releases and reading challenges'
]
</script>

<template>
  <div
    class="min-h-screen bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300 py-16 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto space-y-24">

      <!-- HERO / HEADER -->
      <section class="wow animate__animated animate__fadeIn text-center max-w-3xl mx-auto space-y-6">
        <div
          class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-slate-950/20 dark:border-white/20 bg-paper-light-badge dark:bg-paper-dark-badge text-xs font-bold text-slate-950 dark:text-amber-300 shadow-xs">
          <span>✨ Everything Inside SobdoGolpo</span>
        </div>
        <h1 class="text-4xl sm:text-6xl font-serif font-extrabold text-slate-950 dark:text-amber-50 leading-tight">
          Everything learners need to <br />
          <span class="text-paper-accent dark:text-paper-accent-dark">read, understand & excel</span>
        </h1>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
          SobdoGolpo combines storytelling with interactive evaluation to turn passive reading into active, lifelong
          comprehension skills.
        </p>
      </section>

      <!-- WHAT LEARNERS GET (GRID) -->
      <section class="space-y-12">
        <div class="wow animate__animated animate__fadeInUp text-center space-y-3">
          <h2 class="text-3xl sm:text-4xl font-serif font-bold text-slate-950 dark:text-amber-50">
            Platform Capabilities & Tools
          </h2>
          <p class="text-slate-800 dark:text-slate-200 text-sm sm:text-base font-sans">
            Here is what makes learning effective, engaging, and measurable.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(feature, idx) in coreValueProps" :key="idx"
            class="wow animate__animated animate__fadeInUp p-8 rounded-[2rem] bg-paper-light-card dark:bg-paper-dark-card border border-slate-950/15 dark:border-white/15 shadow-md flex flex-col justify-between space-y-6 hover:scale-[1.02] transition-transform"
            :data-wow-delay="`${idx * 0.1}s`">
            <div class="space-y-4">
              <div class="flex items-center justify-between">
                <span
                  class="size-14 rounded-2xl bg-amber-300/30 dark:bg-amber-400/20 text-3xl flex items-center justify-center">
                  {{ feature.icon }}
                </span>
                <span
                  class="text-[10px] font-bold uppercase tracking-widest px-3 py-1 rounded-full border border-slate-950/10 dark:border-white/10 bg-paper-light-badge dark:bg-paper-dark-badge text-slate-900 dark:text-amber-300">
                  {{ feature.tag }}
                </span>
              </div>
              <h3 class="font-serif font-bold text-xl text-slate-950 dark:text-amber-50">
                {{ feature.title }}
              </h3>
              <p class="text-sm text-slate-800 dark:text-slate-200 leading-relaxed font-sans">
                {{ feature.desc }}
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- HOW WE HELP LEARNERS (LEARNING PILLARS) -->
      <section
        class="p-8 sm:p-12 rounded-[3rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card shadow-xl space-y-12">
        <div class="wow animate__animated animate__fadeIn text-center max-w-2xl mx-auto space-y-3">
          <h2 class="text-3xl sm:text-4xl font-serif font-bold text-slate-950 dark:text-amber-50">
            How We Help Learners Grow
          </h2>
          <p class="text-slate-800 dark:text-slate-200 text-sm sm:text-base font-sans">
            Our 3-step learning framework ensures retention, not just passive scrolling.
          </p>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
          <div v-for="(pillar, idx) in learningPillars" :key="idx"
            class="wow animate__animated animate__fadeInLeft space-y-4 p-6 rounded-2xl border border-slate-950/10 dark:border-white/10 bg-paper-light dark:bg-paper-dark"
            :data-wow-delay="`${idx * 0.15}s`">
            <span class="text-4xl font-serif font-extrabold text-amber-600 dark:text-amber-400">
              {{ pillar.number }}
            </span>
            <h3 class="text-xl font-serif font-bold text-slate-950 dark:text-amber-50">
              {{ pillar.title }}
            </h3>
            <p class="text-sm text-slate-800 dark:text-slate-200 font-sans leading-relaxed">
              {{ pillar.desc }}
            </p>
          </div>
        </div>
      </section>

      <!-- WHAT THEY GET FROM US (SUMMARY BOX) -->
      <section class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
        <div class="lg:col-span-6 wow animate__animated animate__fadeInLeft space-y-6">
          <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50 leading-tight">
            What you get with your subscription
          </h2>
          <p class="text-base text-slate-800 dark:text-slate-200 font-sans leading-relaxed">
            Joining SobdoGolpo gives you an all-in-one suite designed to make reading continuous, measurable, and highly
            rewarding for young minds.
          </p>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
            <div v-for="(item, idx) in inclusions" :key="idx"
              class="flex items-start gap-3 p-3 rounded-xl bg-paper-light-card dark:bg-paper-dark-card border border-slate-950/10 dark:border-white/10 text-xs sm:text-sm font-bold text-slate-950 dark:text-amber-100">
              <span class="text-emerald-600 dark:text-emerald-400 font-black">✓</span>
              <span>{{ item }}</span>
            </div>
          </div>
        </div>

        <div class="lg:col-span-6 wow animate__animated animate__fadeInRight flex justify-center">
          <div
            class="w-full max-w-md p-8 rounded-[2.5rem] bg-slate-950 text-white dark:bg-paper-dark-card dark:text-slate-100 border-2 border-slate-950 dark:border-amber-300/30 shadow-2xl space-y-6">
            <div class="space-y-2">
              <span class="text-xs font-bold text-amber-400 uppercase tracking-widest">Ready to Start?</span>
              <h3 class="text-2xl font-serif font-bold">Try SobdoGolpo Today</h3>
              <p class="text-xs text-slate-300 font-sans">
                Get full access to story collections, adaptive quizzes, and performance reporting.
              </p>
            </div>
            <div class="space-y-3 pt-2">
              <button
                class="w-full py-3.5 rounded-xl bg-amber-400 hover:bg-amber-300 text-slate-950 font-bold transition-transform hover:scale-105 shadow-md">
                Start Free Trial
              </button>
              <button
                class="w-full py-3.5 rounded-xl border border-white/20 bg-transparent text-white dark:text-slate-200 font-bold hover:bg-white/5 transition-all text-xs">
                View Pricing Plans
              </button>
            </div>
          </div>
        </div>
      </section>

    </div>
  </div>
</template>