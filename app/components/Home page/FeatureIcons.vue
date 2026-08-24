<script setup>
import { onMounted } from 'vue'

onMounted(async () => {
    if (import.meta.client) {
        const { default: WOW } = await import('wow.js')
        new WOW({ live: true }).init()
    }
})

const summaryFeatures = [
    { title: 'Engaging Stories', desc: 'Curated library of illustrated short stories and vocabulary adventures.', icon: '📚', bg: 'bg-amber-300/30 dark:bg-amber-400/20 text-slate-950 dark:text-amber-300' },
    { title: 'Instant Quizzes', desc: 'Interactive comprehension questions right after finishing every story.', icon: '⚡', bg: 'bg-amber-400/30 dark:bg-amber-500/20 text-slate-950 dark:text-amber-300' },
    { title: 'Earn & Analyze Marks', desc: 'Instant score breakdowns and detailed visual progress charts.', icon: '🎯', bg: 'bg-emerald-500/20 dark:bg-emerald-400/20 text-emerald-800 dark:text-emerald-300' }
]
</script>

<template>
    <section class="py-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div v-for="(item, idx) in summaryFeatures" :key="idx"
                class="wow animate__animated animate__fadeInUp p-6 rounded-[2rem] bg-paper-light-card dark:bg-paper-dark-card border border-slate-950/15 dark:border-white/15 shadow-xs flex items-start gap-4 hover:scale-105 transition-transform"
                :data-wow-delay="`${idx * 0.15}s`">
                <div :class="`size-12 rounded-full flex items-center justify-center text-2xl shrink-0 ${item.bg}`">
                    {{ item.icon }}
                </div>
                <div>
                    <h3 class="font-serif font-bold text-slate-950 dark:text-amber-50 text-lg mb-1">{{ item.title }}
                    </h3>
                    <p class="text-sm text-slate-800 dark:text-slate-200 leading-relaxed font-sans">{{ item.desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>