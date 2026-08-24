<script setup>
import { onMounted } from 'vue'

onMounted(async () => {
    if (import.meta.client) {
        const { default: WOW } = await import('wow.js')
        new WOW({ live: true }).init()
    }
})

const steps = [
    { id: 1, title: 'Download & Register', desc: 'Create your learner profile in under 30 seconds.' },
    { id: 2, title: 'Pick a Story', desc: 'Choose from hundreds of fun, leveled interactive books.' },
    { id: 3, title: 'Read & Enjoy', desc: 'Tap on difficult words for instant meanings and sound pronunciation.' },
    { id: 4, title: 'Attempt the Quiz', desc: 'Answer quick questions at the end of every chapter.' },
    { id: 5, title: 'Review Your Performance', desc: 'Get instant marks and see weak points highlighted automatically.' }
]
</script>

<template>
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <!-- Left Steps Column -->
            <div class="wow animate__animated animate__fadeInLeft space-y-8">
                <div>
                    <h2 class="text-3xl sm:text-4xl font-serif font-bold text-slate-950 dark:text-amber-50 mb-3">
                        How it works: <br />
                        <span class="text-paper-accent dark:text-paper-accent-dark">Mastering SobdoGolpo</span>
                    </h2>
                    <p class="text-slate-800 dark:text-slate-200 text-sm sm:text-base font-sans">
                        Learning through reading is simple, rewarding, and structured for fast retention.
                    </p>
                </div>

                <div class="space-y-4">
                    <div v-for="step in steps" :key="step.id" class="flex items-start gap-4">
                        <div
                            class="size-8 rounded-full bg-slate-950 dark:bg-amber-300 text-white dark:text-slate-950 font-bold flex items-center justify-center text-sm shrink-0 shadow-md">
                            {{ step.id }}
                        </div>
                        <div>
                            <h4 class="font-serif font-bold text-slate-950 dark:text-amber-50 text-base">{{ step.title
                                }}</h4>
                            <p class="text-xs sm:text-sm text-slate-800 dark:text-slate-200 font-sans">{{ step.desc }}
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right App Frame View -->
            <div class="wow animate__animated animate__fadeInRight flex justify-center">
                <div
                    class="w-[280px] sm:w-[320px] h-[580px] rounded-[3rem] border-8 border-slate-950 dark:border-slate-800 bg-slate-950 p-3 shadow-2xl relative">
                    <!-- Phone Screen Mock -->
                    <div
                        class="w-full h-full bg-paper-light dark:bg-paper-dark rounded-[2.2rem] overflow-hidden p-4 space-y-4 border border-slate-950/10 dark:border-white/10">
                        <div class="w-24 h-4 bg-slate-950/20 dark:bg-white/20 rounded-full mx-auto"></div>
                        <div
                            class="p-3 bg-amber-300/20 dark:bg-amber-400/10 rounded-xl space-y-2 border border-amber-400/30">
                            <span class="text-[10px] font-bold text-amber-700 dark:text-amber-300">TODAY'S TOP
                                STORY</span>
                            <div
                                class="h-20 bg-paper-light-badge dark:bg-paper-dark-card rounded-lg flex items-center justify-center font-serif text-slate-950 dark:text-amber-100 text-xs font-bold">
                                📖 Chapter Preview
                            </div>
                        </div>
                        <div class="space-y-2">
                            <div class="h-3 bg-slate-950/10 dark:bg-white/10 rounded w-full"></div>
                            <div class="h-3 bg-slate-950/10 dark:bg-white/10 rounded w-4/5"></div>
                        </div>
                        <div
                            class="p-3 bg-emerald-500/20 dark:bg-emerald-950/40 rounded-xl border border-emerald-500/40">
                            <span class="text-[10px] font-bold text-emerald-800 dark:text-emerald-300">Quiz Score:
                                95/100</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>