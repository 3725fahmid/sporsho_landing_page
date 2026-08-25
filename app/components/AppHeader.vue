<template>
  <header class="sticky top-0 z-50 w-full pt-4 px-4 sm:px-6 lg:px-8 bg-transparent pointer-events-none">
    <nav class="pointer-events-auto mx-auto flex max-w-6xl items-center justify-between px-6 py-3.5 
              rounded-2xl border border-slate-950/15 dark:border-white/15 
              bg-paper-light-card/80 dark:bg-paper-dark-card/80 
              backdrop-blur-xl backdrop-saturate-150 shadow-xl
              transition-colors duration-300 relative overflow-hidden" aria-label="Global">

      <!-- Subtle top light-edge highlight line -->
      <div
        class="pointer-events-none absolute inset-x-0 top-0 h-px bg-gradient-to-r from-transparent via-slate-950/10 dark:via-white/20 to-transparent">
      </div>

      <!-- Brand Logo -->
      <div class="flex lg:flex-1 items-center">
        <NuxtLink to="/" class="-m-1.5 p-1.5 flex items-center gap-x-2.5 group">
          <span class="sr-only">IC Sporo</span>
          <div
            class="flex size-8 items-center justify-center rounded-lg bg-paper-light-badge dark:bg-paper-dark-icon text-slate-950 dark:text-amber-300 font-extrabold text-base shadow-xs group-hover:scale-105 transition-transform border border-slate-950/10 dark:border-white/10">
            I
          </div>
          <span class="text-base font-extrabold tracking-wider text-slate-950 dark:text-slate-50 font-serif">
            IC SPORO
          </span>
        </NuxtLink>
      </div>

      <!-- Desktop Links Pills Bar -->
      <div
        class="hidden lg:flex lg:gap-x-1 border border-slate-950/10 dark:border-white/15 bg-paper-light/60 dark:bg-paper-dark/60 rounded-full p-1 backdrop-blur-md">
        <NuxtLink to="/"
          class="rounded-full px-4 py-1.5 text-xs font-semibold text-slate-800 dark:text-slate-200 hover:text-slate-950 dark:hover:text-amber-50 hover:bg-slate-950/5 dark:hover:bg-white/10 transition-all duration-200"
          active-class="!bg-paper-light-badge dark:!bg-paper-dark-badge !text-slate-950 dark:!text-amber-300 font-bold">
          Home
        </NuxtLink>
        <NuxtLink to="/features"
          class="rounded-full px-4 py-1.5 text-xs font-semibold text-slate-800 dark:text-slate-200 hover:text-slate-950 dark:hover:text-amber-50 hover:bg-slate-950/5 dark:hover:bg-white/10 transition-all duration-200"
          active-class="!bg-paper-light-badge dark:!bg-paper-dark-badge !text-slate-950 dark:!text-amber-300 font-bold">
          Features
        </NuxtLink>
        <NuxtLink to="/contact"
          class="rounded-full px-4 py-1.5 text-xs font-semibold text-slate-800 dark:text-slate-200 hover:text-slate-950 dark:hover:text-amber-50 hover:bg-slate-950/5 dark:hover:bg-white/10 transition-all duration-200"
          active-class="!bg-paper-light-badge dark:!bg-paper-dark-badge !text-slate-950 dark:!text-amber-300 font-bold">
          Contact
        </NuxtLink>
      </div>

      <!-- Actions (Theme Toggle & CTA) -->
      <div class="hidden lg:flex lg:flex-1 lg:items-center lg:justify-end lg:gap-x-4">
        <button @click="toggleTheme" type="button"
          class="rounded-xl p-2 text-slate-800 dark:text-slate-200 border border-slate-950/10 dark:border-white/15 hover:bg-slate-950/5 dark:hover:bg-white/10 transition-all focus:outline-hidden cursor-pointer"
          :aria-label="isDark ? 'Switch to Light Mode' : 'Switch to Dark Mode'">
          <svg v-if="isDark" class="size-4" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M12 3v2.25m0 13.5V21m8.966-8.966h-2.25M4.286 12H2.036m15.357-6.364l-1.591 1.591M6.759 17.241l-1.591 1.591m12.728 0l-1.591-1.591M6.759 6.759L5.168 5.168M12 8.25a3.75 3.75 0 100 7.5 3.75 3.75 0 000-7.5z" />
          </svg>
          <svg v-else class="size-4" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
          </svg>
        </button>

        <NuxtLink to="/contact"
          class="rounded-xl bg-slate-950 dark:bg-paper-accent-dark text-white dark:text-slate-950 px-4 py-2 text-xs font-bold border border-slate-950 dark:border-amber-300/40 hover:scale-105 shadow-xs transition-all duration-200">
          Book a demo
        </NuxtLink>
      </div>

      <!-- Mobile Buttons -->
      <div class="flex items-center gap-x-2 lg:hidden">
        <button @click="toggleTheme" type="button"
          class="rounded-lg p-2 text-slate-800 dark:text-slate-200 hover:bg-slate-950/5 dark:hover:bg-white/10">
          <svg v-if="isDark" class="size-5" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M12 3v2.25m0 13.5V21m8.966-8.966h-2.25M4.286 12H2.036m15.357-6.364l-1.591 1.591M6.759 17.241l-1.591 1.591m12.728 0l-1.591-1.591M6.759 6.759L5.168 5.168M12 8.25a3.75 3.75 0 100 7.5 3.75 3.75 0 000-7.5z" />
          </svg>
          <svg v-else class="size-5" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
          </svg>
        </button>

        <button @click="isOpen = !isOpen" type="button"
          class="inline-flex items-center justify-center rounded-lg p-2 text-slate-800 dark:text-slate-200 hover:bg-slate-950/5 dark:hover:bg-white/10">
          <span class="sr-only">Open main menu</span>
          <svg v-if="!isOpen" class="size-6" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
          <svg v-else class="size-6" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
    </nav>

    <!-- Mobile Drawer Menu -->
    <Transition enter-active-class="transition duration-200 ease-out" enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0" leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 -translate-y-2">
      <div v-if="isOpen"
        class="pointer-events-auto mt-2 mx-auto max-w-6xl rounded-2xl border border-slate-950/15 dark:border-white/15 bg-paper-light-card/95 dark:bg-paper-dark-card/95 p-6 backdrop-blur-xl shadow-2xl lg:hidden">
        <div class="space-y-1">
          <NuxtLink to="/" @click="isOpen = false"
            class="block rounded-xl px-3 py-2.5 text-base font-semibold text-slate-900 dark:text-slate-100 hover:bg-slate-950/5 dark:hover:bg-white/10">
            Home
          </NuxtLink>
          <NuxtLink to="/features" @click="isOpen = false"
            class="block rounded-xl px-3 py-2.5 text-base font-semibold text-slate-900 dark:text-slate-100 hover:bg-slate-950/5 dark:hover:bg-white/10">
            Features
          </NuxtLink>
          <NuxtLink to="/contact" @click="isOpen = false"
            class="block rounded-xl px-3 py-2.5 text-base font-semibold text-slate-900 dark:text-slate-100 hover:bg-slate-950/5 dark:hover:bg-white/10">
            Contact
          </NuxtLink>
        </div>
        <div class="mt-6">
          <NuxtLink to="/contact" @click="isOpen = false"
            class="block w-full rounded-xl bg-slate-950 dark:bg-paper-accent-dark py-2.5 text-center text-sm font-bold text-white dark:text-slate-950 border border-slate-950 dark:border-amber-300/40 shadow-xs">
            Book a demo
          </NuxtLink>
        </div>
      </div>
    </Transition>
  </header>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const isOpen = ref(false);
const isDark = ref(true);

const toggleTheme = () => {
  isDark.value = !isDark.value;
  if (isDark.value) {
    document.documentElement.classList.add('dark');
    localStorage.setItem('theme', 'dark');
  } else {
    document.documentElement.classList.remove('dark');
    localStorage.setItem('theme', 'light');
  }
};

onMounted(() => {
  isDark.value = document.documentElement.classList.contains('dark');
});
</script>