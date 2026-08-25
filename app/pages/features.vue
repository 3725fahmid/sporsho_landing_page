<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (import.meta.client && window.WOW) {
    new window.WOW({
      boxClass: 'wow',
      animateClass: 'animate__animated',
      offset: 100,
      mobile: true,
      live: true
    }).init()
  }
})

const featuresList = [
  {
    title: 'AI Document Summarizer',
    desc: 'Extract multi-page document summaries, key findings, and actionable steps in seconds.',
    icon: 'M12 6.042A8.967 8.967 0 006 3.75c-1.052 0-2.062.18-3 .512v14.25A8.987 8.987 0 016 18c2.305 0 4.408.867 6 2.292m0-14.25a8.966 8.966 0 016-2.292c1.052 0 2.062.18 3 .512v14.25A8.987 8.987 0 0018 18a8.967 8.967 0 00-6 2.292m0-14.25v14.25'
  },
  {
    title: 'High-Precision OCR Engine',
    desc: 'Turn non-searchable scanned PDFs and image files into crisp, editable text instantly.',
    icon: 'M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z'
  },
  {
    title: 'Smart Annotation Layer',
    desc: 'Highlight text, draw diagrams, drop sticky notes, and manage all your reader markups.',
    icon: 'M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10'
  },
  {
    title: 'Seamless File Conversion',
    desc: 'Convert PDF files to Word, Excel, JPG, and Markdown without losing formatting or tables.',
    icon: 'M7.5 21L3 16.5m0 0L7.5 12M3 16.5h13.5m0-13.5L21 7.5m0 0L16.5 12M21 7.5H7.5'
  },
  {
    title: 'Multi-Device Synchronization',
    desc: 'Read on Desktop, web, or mobile with automatic sync of reading progress and notes.',
    icon: 'M12 16.5V9.75m0 0l3 3m-3-3l-3 3M6.75 19.5a4.5 4.5 0 01-1.41-8.775 5.25 5.25 0 0110.233-2.33 3 3 0 013.758 3.848A3.75 3.75 0 0118 19.5H6.75z'
  },
  {
    title: 'AES 256-Bit Security',
    desc: 'Keep private records and legal documents safe with local-first processing and encryption.',
    icon: 'M16.5 10.5V6.75a4.5 4.5 0 10-9 0v3.75m-.75 11.25h10.5a2.25 2.25 0 002.25-2.25v-6.75a2.25 2.25 0 00-2.25-2.25H6.75a2.25 2.25 0 00-2.25 2.25v6.75a2.25 2.25 0 002.25 2.25z'
  }
]
</script>

<template>
  <div
    class="bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300 min-h-screen py-16 px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">

      <!-- HERO -->
      <div class="wow animate__animated animate__fadeInDown text-center max-w-3xl mx-auto mb-20 space-y-4">
        <h1 class="text-4xl sm:text-6xl font-serif font-bold text-slate-950 dark:text-amber-50">
          Features Built for Readers & Researchers
        </h1>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
          Everything you need to read, analyze, and synthesize documents faster than ever before.
        </p>
      </div>

      <!-- FEATURES GRID -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(feature, idx) in featuresList" :key="idx"
          class="wow animate__animated animate__fadeInUp p-8 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card shadow-md hover:scale-105 transition-all duration-300"
          :data-wow-delay="`${(idx % 3) * 0.2}s`">
          <div
            class="size-12 rounded-full bg-paper-light-badge dark:bg-paper-dark-icon text-slate-950 dark:text-amber-300 flex items-center justify-center mb-6">
            <svg class="size-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" :d="feature.icon" />
            </svg>
          </div>
          <h3 class="text-2xl font-serif font-bold text-slate-950 dark:text-amber-50 mb-3">{{ feature.title }}</h3>
          <p class="text-sm text-slate-800 dark:text-slate-200 font-sans leading-relaxed">{{ feature.desc }}</p>
        </div>
      </div>

    </div>
  </div>
</template>