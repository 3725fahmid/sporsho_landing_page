<script setup>
import { ref } from 'vue'
import emblaCarouselVue from 'embla-carousel-vue'

// Initialize Embla Carousel with options
const [emblaRef, emblaApi] = emblaCarouselVue({
    loop: false,
    align: 'start',
    slidesToScroll: 1
})

const canScrollPrev = ref(false)
const canScrollNext = ref(false)

const scrollPrev = () => emblaApi.value && emblaApi.value.scrollPrev()
const scrollNext = () => emblaApi.value && emblaApi.value.scrollNext()

const updateScrollState = () => {
    if (!emblaApi.value) return
    canScrollPrev.value = emblaApi.value.canScrollPrev()
    canScrollNext.value = emblaApi.value.canScrollNext()
}

onMounted(() => {
    if (emblaApi.value) {
        emblaApi.value.on('select', updateScrollState)
        emblaApi.value.on('reInit', updateScrollState)
        updateScrollState()
    }
})

const selectedCategory = ref('All')
const categories = ['All', 'Folktales', 'Science', 'History', 'Vocabulary']

const stories = [
    { id: 1, title: 'The Wise Crow', category: 'Folktales', level: 'Beginner', questions: 5, bg: 'bg-amber-200/40 dark:bg-amber-950/40' },
    { id: 2, title: 'Solar System Voyage', category: 'Science', level: 'Intermediate', questions: 8, bg: 'bg-emerald-200/40 dark:bg-emerald-950/40' },
    { id: 3, title: 'The Ancient Kingdom', category: 'History', level: 'Advanced', questions: 10, bg: 'bg-amber-300/30 dark:bg-amber-900/40' },
    { id: 4, title: 'Everyday Word Mastery', category: 'Vocabulary', level: 'Beginner', questions: 6, bg: 'bg-rose-200/40 dark:bg-rose-950/40' },
    { id: 5, title: 'The Clever Rabbit', category: 'Folktales', level: 'Beginner', questions: 4, bg: 'bg-amber-200/40 dark:bg-amber-950/40' },
    { id: 6, title: 'The Wise Crow', category: 'Folktales', level: 'Beginner', questions: 5, bg: 'bg-amber-200/40 dark:bg-amber-950/40' },
    { id: 7, title: 'Solar System Voyage', category: 'Science', level: 'Intermediate', questions: 8, bg: 'bg-emerald-200/40 dark:bg-emerald-950/40' },
    { id: 8, title: 'The Ancient Kingdom', category: 'History', level: 'Advanced', questions: 10, bg: 'bg-amber-300/30 dark:bg-amber-900/40' },
    { id: 9, title: 'Everyday Word Mastery', category: 'Vocabulary', level: 'Beginner', questions: 6, bg: 'bg-rose-200/40 dark:bg-rose-950/40' },
    { id: 10, title: 'The Clever Rabbit', category: 'Folktales', level: 'Beginner', questions: 4, bg: 'bg-amber-200/40 dark:bg-amber-950/40' }
]

const filteredStories = () => {
    if (selectedCategory.value === 'All') return stories
    return stories.filter(story => story.category === selectedCategory.value)
}
</script>

<template>
    <section class="py-20 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto space-y-8">
        <!-- Header Controls -->
        <div class="wow animate__animated animate__fadeInUp flex flex-col items-center justify-between gap-6">
            <div class="space-y-2 text-center md:text-left">
                <h2 class="text-3xl sm:text-5xl font-serif font-bold text-slate-950 dark:text-amber-50">
                    Explore Interactive Stories
                </h2>
                <p class="text-sm sm:text-base text-slate-800 dark:text-slate-200 font-sans">
                    Swipe through stories, attempt instant quizzes, and earn score marks.
                </p>
            </div>

            <!-- Navigation & Category Filters -->
            <div class="flex items-center gap-4">
                <!-- Category Filter -->
                <!-- Category Filter Container -->
                <div class="w-full overflow-x-auto no-scrollbar scroll-smooth -mx-4 px-4 sm:mx-0 sm:px-0 py-2">
                    <div class="flex items-center gap-2 w-max">
                        <button v-for="cat in categories" :key="cat" @click="selectedCategory = cat" :class="[
                            'px-4 py-2 sm:py-1.5 rounded-full text-xs font-bold transition-all cursor-pointer whitespace-nowrap shrink-0 active:scale-95',
                            selectedCategory === cat
                                ? 'bg-slate-950 text-white dark:bg-amber-300 dark:text-slate-950 shadow-md'
                                : 'bg-paper-light-card dark:bg-paper-dark-card text-slate-800 dark:text-slate-200 border border-slate-950/15 dark:border-white/15 hover:bg-slate-200 dark:hover:bg-slate-800'
                        ]">
                            {{ cat }}
                        </button>
                    </div>
                </div>

            </div>
        </div>
        <section
            class="p-4 sm:p-12 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card shadow-xl space-y-12">
            <!-- Carousel Navigation Arrows -->
            <div class="hidden sm:flex items-center gap-2.5">
                <!-- Previous Button -->
                <button @click="scrollPrev" :disabled="!canScrollPrev"
                    class="size-11 rounded-full border border-slate-950/15 dark:border-white/15 bg-paper-light-card/80 dark:bg-paper-dark-card/80 backdrop-blur-md text-slate-900 dark:text-amber-300 flex items-center justify-center transition-all duration-200 hover:bg-slate-950 hover:text-white dark:hover:bg-amber-300 dark:hover:text-slate-950 hover:shadow-lg hover:shadow-slate-950/10 dark:hover:shadow-amber-300/20 active:scale-95 disabled:opacity-25 disabled:pointer-events-none cursor-pointer"
                    aria-label="Previous Slide">
                    <svg class="size-5 transition-transform duration-200 group-hover:-translate-x-0.5" fill="none"
                        viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
                    </svg>
                </button>

                <!-- Next Button -->
                <button @click="scrollNext" :disabled="!canScrollNext"
                    class="size-11 rounded-full border border-slate-950/15 dark:border-white/15 bg-paper-light-card/80 dark:bg-paper-dark-card/80 backdrop-blur-md text-slate-900 dark:text-amber-300 flex items-center justify-center transition-all duration-200 hover:bg-slate-950 hover:text-white dark:hover:bg-amber-300 dark:hover:text-slate-950 hover:shadow-lg hover:shadow-slate-950/10 dark:hover:shadow-amber-300/20 active:scale-95 disabled:opacity-25 disabled:pointer-events-none cursor-pointer"
                    aria-label="Next Slide">
                    <svg class="size-5 transition-transform duration-200 group-hover:translate-x-0.5" fill="none"
                        viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
                    </svg>
                </button>
            </div>
            <!-- Embla Viewport Container -->
            <div class="overflow-hidden cursor-grab active:cursor-grabbing" ref="emblaRef">
                <div class="flex gap-6">
                    <div v-for="story in filteredStories()" :key="story.id"
                        class="flex-[0_0_85%] sm:flex-[0_0_45%] lg:flex-[0_0_30%] min-w-0">
                        <div
                            class="h-full p-6 rounded-[2rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card flex flex-col justify-between space-y-6 shadow-md hover:scale-[1.02] transition-transform">
                            <div class="space-y-4">
                                <div
                                    :class="`h-36 rounded-2xl flex items-center justify-center font-serif font-bold text-2xl text-slate-950 dark:text-amber-100 ${story.bg}`">
                                    📖 {{ story.category }}
                                </div>
                                <div>
                                    <span
                                        class="text-[10px] font-bold uppercase tracking-wider text-amber-700 dark:text-amber-400">
                                        {{ story.level }}
                                    </span>
                                    <h3 class="text-xl font-serif font-bold text-slate-950 dark:text-amber-50 mt-1">
                                        {{ story.title }}
                                    </h3>
                                </div>
                            </div>

                            <div
                                class="pt-4 border-t border-slate-950/10 dark:border-white/10 flex items-center justify-between text-xs font-bold text-slate-800 dark:text-slate-200">
                                <span>🎯 {{ story.questions }} Questions</span>
                                <button
                                    class="px-4 py-2 rounded-xl bg-slate-950 text-white dark:bg-amber-300 dark:text-slate-950 hover:scale-105 transition-transform">
                                    Start Quiz
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </section>
</template>