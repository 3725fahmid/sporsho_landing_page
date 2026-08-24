<script setup>
import { ref } from 'vue'

const activeFaq = ref(0)

const faqs = [
    {
        question: 'How does the quiz system evaluate my reading performance?',
        answer: 'After reading each story chapter, you answer multiple-choice questions. The system calculates your score based on accuracy and speed, then automatically highlights your weak topics.'
    },
    {
        question: 'Can I use SobdoGolpo offline?',
        answer: 'Yes! Pro Scholar members can download story packs and quizzes for offline access anytime without internet connectivity.'
    },
    {
        question: 'Is SobdoGolpo suitable for all age groups?',
        answer: 'Absolutely. We offer tailored story levels ranging from beginner vocabulary to advanced comprehension modules for older readers.'
    },
    {
        question: 'Can teachers or parents track performance stats?',
        answer: 'Yes, with our Team & School plan, parents and educators receive detailed progress dashboards and performance breakdown reports.'
    }
]

const toggleFaq = (index) => {
    activeFaq.value = activeFaq.value === index ? null : index
}
</script>

<template>
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
            <!-- Title Column -->
            <div class="lg:col-span-5 wow animate__animated animate__fadeInLeft space-y-4">
                <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50 leading-tight">
                    Frequently Asked Questions
                </h2>
                <p class="text-base text-slate-800 dark:text-slate-200 font-sans">
                    Have questions about how SobdoGolpo works? Here are answers to the most common queries.
                </p>
            </div>

            <!-- Accordion Column -->
            <div class="lg:col-span-7 wow animate__animated animate__fadeInRight space-y-4">
                <div v-for="(faq, index) in faqs" :key="index"
                    class="rounded-2xl border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card overflow-hidden shadow-xs transition-all">
                    <button @click="toggleFaq(index)" type="button"
                        class="w-full p-6 text-left flex justify-between items-center gap-4 cursor-pointer">
                        <span class="font-serif font-bold text-lg text-slate-950 dark:text-amber-50">
                            {{ faq.question }}
                        </span>
                        <span
                            class="size-8 rounded-full border border-slate-950/20 dark:border-white/20 flex items-center justify-center shrink-0 font-bold text-slate-950 dark:text-amber-300">
                            {{ activeFaq === index ? '−' : '+' }}
                        </span>
                    </button>
                    <div v-if="activeFaq === index"
                        class="px-6 pb-6 text-sm leading-relaxed text-slate-800 dark:text-slate-200 font-sans border-t border-slate-950/10 dark:border-white/10 pt-4">
                        {{ faq.answer }}
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>