<script setup>
import { ref } from 'vue'

const showAllFeatures = ref(false)

const features = [
  {
    title: 'Instant Reading Mode',
    description: 'Load multi-thousand page documents seamlessly with zero lag and customizable page-turning views.',
    iconPath: 'M12 6.042A8.967 8.967 0 006 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 016 18c2.305 0 4.408.867 6 2.292m0-14.25a8.966 8.966 0 016-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0018 18a8.967 8.967 0 00-6 2.292m0-14.25v14.25'
  },
  {
    title: 'Smart AI Annotation',
    description: 'Highlight text, add sticky notes, drawing overlays, and generate auto-summaries instantly.',
    iconPath: 'M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10'
  },
  {
    title: 'PDF Conversion & Export',
    description: 'Convert PDFs to Word, Excel, images, and text formats effortlessly without formatting loss.',
    iconPath: 'M7.5 21L3 16.5m0 0L7.5 12M3 16.5h13.5m0-13.5L21 7.5m0 0L16.5 12M21 7.5H7.5'
  },
  {
    title: 'Cloud & Multi-Device Sync',
    description: 'Access your paper collection across Desktop, Web, and Mobile with real-time reading progress.',
    iconPath: 'M12 16.5V9.75m0 0l3 3m-3-3l-3 3M6.75 19.5a4.5 4.5 0 01-1.41-8.775 5.25 5.25 0 0110.233-2.33 3 3 0 013.758 3.848A3.75 3.75 0 0118 19.5H6.75z'
  },
  {
    title: 'OCR Text Recognition',
    description: 'Extract editable text from scanned PDF documents and images using high-precision AI OCR.',
    iconPath: 'M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z'
  },
  {
    title: 'Bank-Grade Security',
    description: 'Protect confidential documents with AES 256-bit password encryption and permission controls.',
    iconPath: 'M16.5 10.5V6.75a4.5 4.5 0 10-9 0v3.75m-.75 11.25h10.5a2.25 2.25 0 002.25-2.25v-6.75a2.25 2.25 0 00-2.25-2.25H6.75a2.25 2.25 0 00-2.25 2.25v6.75a2.25 2.25 0 002.25 2.25z'
  }
]

const valueProps = [
  { title: 'No Installation Needed', desc: 'Use directly in browser or install native lightweight desktop app.', icon: 'M13.5 16.875h3.375m0 0h3.375m-3.375 0V13.5m0 3.375v3.375M6 10.5h2.25a2.25 2.25 0 002.25-2.25V6a2.25 2.25 0 00-2.25-2.25H6A2.25 2.25 0 003.75 6v2.25A2.25 2.25 0 006 10.5z' },
  { title: 'Lightning Fast Engine', desc: 'Render giant medical or engineering PDFs in less than a second.', icon: 'M3.75 13.5l10.5-11.25L12 10.5h8.25L9.75 21.75 12 13.5H3.75z' },
  { title: 'Regular Free Updates', desc: 'Continuous improvements and new reading capabilities every month.', icon: 'M16.023 9.348h4.992v-.001M2.985 19.644v-4.992m0 0h4.992m-4.993 0l3.181 3.183a8.25 8.25 0 0013.803-3.7M4.031 9.865a8.25 8.25 0 0113.803-3.7l3.181 3.182m0-4.991v4.99' },
  { title: '24/7 Dedicated Support', desc: 'Instant support for file recovery, licensing, and workflow setup.', icon: 'M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z' }
]

const plans = [
  { name: 'Basic', price: '$4.99', desc: 'Perfect for students and casual readers.', features: ['Fast PDF Rendering', 'Basic Annotations', '1 GB Cloud Storage', 'Standard Support'], highlight: false },
  { name: 'Pro', price: '$9.99', desc: 'Best value for professionals and researchers.', features: ['All Basic Features', 'AI Document Summarizer', 'OCR Text Recognition', '50 GB Cloud Sync', 'Priority Support'], highlight: true },
  { name: 'Enterprise', price: '$19.99', desc: 'Full power for teams and organization setups.', features: ['All Pro Features', 'Unlimited Cloud Sync', 'AES 256 Encryption', 'Multi-Device License', '24/7 VIP Support'], highlight: false }
]
</script>

<template>
  <div
    class="min-h-screen bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300">

    <!-- HERO SECTION -->
    <section
      class="relative py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <div class="space-y-6 text-center lg:text-left">
        <div
          class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full border border-slate-950/20 dark:border-white/20 bg-paper-light-badge dark:bg-paper-dark-badge text-xs font-bold text-slate-900 dark:text-amber-300 shadow-xs">
          <span>📄 Next-Gen PDF Experience</span>
        </div>
        <h1
          class="text-4xl sm:text-6xl font-serif font-bold tracking-tight text-slate-950 dark:text-amber-50 leading-tight">
          The Best PDF Reader for Pro Workflows <br />
          <span class="text-paper-accent dark:text-paper-accent-dark">IC Sporo</span>
        </h1>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 max-w-xl mx-auto lg:mx-0 font-sans">
          IC Sporo gives you complete control over your PDFs. Read, annotate, summarize with AI, and sign documents
          effortlessly with paper-like feel and speed.
        </p>
        <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4">
          <button
            class="px-8 py-3.5 rounded-2xl border-2 border-slate-950 dark:border-amber-300/40 bg-slate-950 text-white dark:bg-paper-accent-dark dark:text-slate-950 font-bold hover:scale-105 transition-all shadow-md">
            Download Now
          </button>
          <button
            class="px-8 py-3.5 rounded-2xl border-2 border-slate-950/20 dark:border-white/20 bg-paper-light-card dark:bg-paper-dark-card text-slate-950 dark:text-slate-100 font-bold hover:scale-105 transition-all">
            Explore Demo
          </button>
        </div>
      </div>

      <!-- Hero Visual -->
      <div class="relative flex justify-center">
        <div
          class="w-full max-w-md p-6 rounded-[2.5rem] border-2 border-slate-950/20 dark:border-white/20 bg-paper-light-card dark:bg-paper-dark-card shadow-2xl hover:scale-105 transition-transform duration-300">
          <div
            class="p-6 rounded-[1.5rem] border border-slate-950/15 dark:border-white/15 bg-paper-light/80 dark:bg-paper-dark-preview space-y-4">
            <div class="flex items-center justify-between border-b border-slate-950/10 dark:border-white/10 pb-3">
              <span class="font-serif font-bold text-sm text-slate-950 dark:text-slate-50">Document_Report.pdf</span>
              <span
                class="text-xs bg-amber-300 dark:bg-amber-400 text-slate-950 px-2.5 py-0.5 rounded-full font-bold">PDF
                Reader</span>
            </div>
            <div class="space-y-2 font-sans text-xs">
              <div class="h-3 bg-slate-300 dark:bg-slate-700 rounded w-3/4"></div>
              <div class="h-3 bg-slate-300 dark:bg-slate-700 rounded w-full"></div>
              <div class="h-3 bg-amber-400/80 dark:bg-amber-500/80 rounded w-5/6"></div>
              <div class="h-3 bg-slate-300 dark:bg-slate-700 rounded w-2/3"></div>
            </div>
            <div class="pt-2 flex justify-between items-center text-xs font-bold text-slate-900 dark:text-amber-300">
              <span>Page 1 of 124</span>
              <span>100% Zoom</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- AMAZING FEATURES SECTION -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Amazing Features
        </h2>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
          IC Sporo delivers powerful reading tools engineered for speed, privacy, and full document productivity.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 items-stretch">
        <template v-for="(item, index) in features" :key="index">
          <div v-if="index < 3 || showAllFeatures"
            class="group relative p-8 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card shadow-md hover:shadow-2xl hover:scale-105 hover:z-30 transition-all duration-300 flex flex-col justify-between">
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
        <button @click="showAllFeatures = !showAllFeatures" type="button"
          class="inline-flex items-center justify-center gap-x-2 rounded-2xl border-2 border-slate-950/30 dark:border-amber-300/40 bg-paper-light-card dark:bg-paper-dark-badge px-10 py-3.5 text-sm font-bold text-slate-950 dark:text-amber-200 shadow-md transition-all duration-200 hover:bg-slate-200 dark:hover:bg-paper-dark-icon hover:scale-105 cursor-pointer">
          <span>{{ showAllFeatures ? 'Show Less' : 'Learn More' }}</span>
          <svg class="size-4 transition-transform duration-200" :class="showAllFeatures ? 'rotate-180' : ''" fill="none"
            stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
          </svg>
        </button>
      </div>
    </section>

    <!-- WHY CHOOSE SECTION -->
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
      <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Why Choose IC Sporo?
        </h2>
        <p class="text-base text-slate-800 dark:text-slate-200 font-sans">Built for researchers, students, and
          document-heavy teams.</p>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div v-for="(vp, idx) in valueProps" :key="idx"
          class="p-6 rounded-[2rem] border border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card text-center space-y-3 hover:scale-105 transition-transform shadow-xs">
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
      <div class="text-center max-w-3xl mx-auto mb-16 space-y-3">
        <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Simple & Affordable Pricing
        </h2>
        <p class="text-base text-slate-800 dark:text-slate-200 font-sans">Choose the best plan that fits your reading
          needs.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-stretch">
        <div v-for="(plan, idx) in plans" :key="idx"
          :class="plan.highlight ? 'border-amber-600 dark:border-amber-400 border-4 scale-105' : 'border-2 border-slate-950/15 dark:border-white/15'"
          class="p-8 rounded-[2rem] bg-paper-light-card dark:bg-paper-dark-card flex flex-col justify-between shadow-lg hover:scale-105 transition-transform">
          <div class="space-y-4">
            <h3 class="text-2xl font-serif font-bold text-slate-950 dark:text-amber-50">{{ plan.name }}</h3>
            <div class="text-4xl font-serif font-bold text-paper-accent dark:text-paper-accent-dark">{{ plan.price
              }}<span class="text-xs font-sans text-slate-700 dark:text-slate-300">/month</span></div>
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
        class="p-10 rounded-[2.5rem] bg-slate-950 dark:bg-paper-dark-card border-2 border-slate-950 dark:border-amber-300/30 text-center space-y-6 shadow-2xl">
        <h2 class="text-3xl sm:text-4xl font-serif font-bold text-amber-100">Ready to Upgrade Your PDF Workflow?</h2>
        <p class="text-sm text-slate-200 max-w-xl mx-auto font-sans">Get started with IC Sporo today and experience
          paper-like PDF reading with AI capabilities.</p>
        <button
          class="px-10 py-3.5 rounded-2xl bg-paper-light-badge dark:bg-paper-accent-dark text-slate-950 font-bold hover:scale-105 transition-transform text-sm shadow-md">
          Download IC Sporo Free
        </button>
      </div>
    </section>

  </div>
</template>