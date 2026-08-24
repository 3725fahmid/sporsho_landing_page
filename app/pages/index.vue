<script setup>
import FaqAccordion from '~/components/Home page/FaqAccordion.vue';
import FeatureIcons from '~/components/Home page/FeatureIcons.vue';
import HeroBanner from '~/components/Home page/HeroBanner.vue';
import HowItWorks from '~/components/Home page/HowItWorks.vue';
import StoryCatalog from '~/components/Home page/StoryCatalog.vue';


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
  <div
    class="min-h-screen bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300">
    <!-- HERO SECTION -->
    <HeroBanner />

    <!-- 3-COLUMN FEATURE HIGHLIGHTS -->
    <FeatureIcons />

    <!-- HOW IT WORKS & APP MOCKUP -->
    <HowItWorks />

    <!-- STORY CATALOG GRID -->
    <StoryCatalog />

    <!-- FAQ ACCORDION SECTION -->
    <FaqAccordion />
  </div>
</template>