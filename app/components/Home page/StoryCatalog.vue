<script setup>
import { ref } from 'vue'

const selectedCategory = ref('All')
const categories = ['All', 'Folktales', 'Science', 'History', 'Vocabulary']

const stories = [
    { id: 1, title: 'The Wise Crow', category: 'Folktales', level: 'Beginner', questions: 5, bg: 'bg-amber-100 dark:bg-amber-950/40' },
    { id: 2, title: 'Solar System Voyage', category: 'Science', level: 'Intermediate', questions: 8, bg: 'bg-emerald-100 dark:bg-emerald-950/40' },
    { id: 3, title: 'The Ancient Kingdom', category: 'History', level: 'Advanced', questions: 10, bg: 'bg-indigo-100 dark:bg-indigo-950/40' },
    { id: 4, title: 'Everyday Word Mastery', category: 'Vocabulary', level: 'Beginner', questions: 6, bg: 'bg-rose-100 dark:bg-rose-950/40' }
]

const filteredStories = () => {
    if (selectedCategory.value === 'All') return stories
    return stories.filter(story => story.category === selectedCategory.value)
}
</script>

<template>
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        <!-- Header -->
        <div class="wow animate__animated animate__fadeInUp text-center max-w-3xl mx-auto mb-12 space-y-3">
            <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
                Explore Exciting Story Categories
            </h2>
            <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
                Pick a topic, read engaging chapters, and attempt interactive quizzes to earn your score.
            </p>

            <!-- Category Tabs -->
            <div class="flex flex-wrap items-center justify-center gap-2 pt-4">
                <button v-for="cat in categories" :key="cat" @click="selectedCategory = cat" :class="[
                    'px-5 py-2 rounded-full text-xs font-bold transition-all duration-200 cursor-pointer',
                    selectedCategory === cat
                        ? 'bg-slate-950 text-white dark:bg-amber-300 dark:text-slate-950 shadow-md'
                        : 'bg-paper-light-card dark:bg-paper-dark-card text-slate-800 dark:text-slate-200 border border-slate-950/15 dark:border-white/15'
                ]">
                    {{ cat }}
                </button>
            </div>
        </div>

        <!-- Cards Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            <div v-for="(story, idx) in filteredStories()" :key="story.id"
                class="wow animate__animated animate__zoomIn p-6 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card flex flex-col justify-between hover:scale-105 transition-all shadow-md"
                :data-wow-delay="`${idx * 0.15}s`">
                <div class="space-y-4">
                    <div
                        :class="`h-32 rounded-2xl flex items-center justify-center font-serif font-bold text-2xl text-slate-950 dark:text-amber-100 ${story.bg}`">
                        📖 {{ story.category }}
                    </div>
                    <div>
                        <span class="text-[10px] font-bold uppercase tracking-wider text-amber-600 dark:text-amber-400">
                            {{ story.level }}
                        </span>
                        <h3 class="text-xl font-serif font-bold text-slate-950 dark:text-amber-50 mt-1">
                            {{ story.title }}
                        </h3>
                    </div>
                </div>

                <div
                    class="pt-6 border-t border-slate-950/10 dark:border-white/10 flex items-center justify-between text-xs font-bold text-slate-800 dark:text-slate-200">
                    <span>🎯 {{ story.questions }} Questions</span>
                    <button
                        class="px-4 py-2 rounded-xl bg-paper-light-badge dark:bg-paper-dark-badge text-slate-950 dark:text-amber-200 hover:scale-105 transition-transform">
                        Start Quiz
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>