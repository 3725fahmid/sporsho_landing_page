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
</script>

<template>
    <section
        class="relative py-16 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Left Text Column -->
        <div class="wow animate__animated animate__fadeInLeft space-y-6 text-center lg:text-left">
            <div
                class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-slate-950/20 dark:border-white/20 bg-paper-light-badge dark:bg-paper-dark-badge text-xs font-bold text-slate-900 dark:text-amber-300 shadow-xs">
                <span>🎮 Playful Learning Experience</span>
            </div>
            <h1 class="text-4xl sm:text-6xl font-serif font-extrabold text-slate-950 dark:text-amber-50 leading-tight">
                Transforming reading into <br />
                <span class="text-paper-accent dark:text-paper-accent-dark">playful adventures</span>
            </h1>
            <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 max-w-xl mx-auto lg:mx-0 font-sans">
                SobdoGolpo turns storytime into interactive games. Read captivating stories, take instant quizzes, earn
                marks, and watch your skills grow every day!
            </p>
            <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4 pt-2">
                <button
                    class="px-8 py-3.5 rounded-2xl border-2 border-slate-950 dark:border-amber-300/40 bg-slate-950 text-white dark:bg-paper-accent-dark dark:text-slate-950 font-bold hover:scale-105 transition-all shadow-md">
                    Get Started Free
                </button>
                <button
                    class="px-8 py-3.5 rounded-2xl border-2 border-slate-950/20 dark:border-white/20 bg-paper-light-card dark:bg-paper-dark-card text-slate-950 dark:text-slate-100 font-bold hover:scale-105 transition-all">
                    Explore Stories
                </button>
            </div>
        </div>

        <!-- Right Mockup Visual -->
        <div class="wow animate__animated animate__fadeInRight relative flex justify-center">
            <div
                class="w-full max-w-md p-6 rounded-[2.5rem] bg-gradient-to-tr from-amber-500 to-amber-700 shadow-2xl shadow-amber-500/20 relative">
                <div class="p-6 rounded-[1.8rem] bg-paper-light dark:bg-paper-dark space-y-4 shadow-inner">
                    <div
                        class="flex items-center justify-between border-b border-slate-950/10 dark:border-white/10 pb-3">
                        <span class="text-xs font-bold text-amber-700 dark:text-amber-300">🔥 5-Day Quiz Streak</span>
                        <span
                            class="text-xs bg-emerald-500/20 text-emerald-800 dark:text-emerald-300 px-2.5 py-0.5 rounded-full font-bold">Passed</span>
                    </div>
                    <div class="space-y-3">
                        <h4 class="font-serif font-bold text-slate-950 dark:text-slate-100 text-sm">Story Chapter: The
                            Wise Crow</h4>
                        <div
                            class="p-3.5 rounded-xl bg-paper-light-card dark:bg-paper-dark-card border border-slate-950/15 dark:border-white/15 space-y-2">
                            <p class="text-xs text-slate-800 dark:text-slate-200 font-medium">Q: How did the crow reach
                                the water level?</p>
                            <div
                                class="p-2 rounded-lg bg-emerald-600 text-white text-xs font-bold flex justify-between">
                                <span>✓ By dropping pebbles</span>
                                <span>+15 Marks</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>