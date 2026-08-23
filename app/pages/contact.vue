<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (import.meta.client && window.WOW) {
    new window.WOW({
      boxClass: 'wow',
      animateClass: 'animate__animated',
      offset: 50,
      mobile: true,
      live: true
    }).init()
  }
})
</script>

<template>
  <div
    class="bg-paper-light dark:bg-paper-dark text-slate-950 dark:text-slate-50 transition-colors duration-300 min-h-screen py-16 px-6 lg:px-8">

    <div class="mx-auto max-w-6xl">

      <!-- HEADER TITLE -->
      <div class="wow animate__animated animate__fadeInDown text-center max-w-2xl mx-auto mb-16 space-y-4">
        <div
          class="inline-flex items-center gap-x-2 rounded-full bg-paper-light-badge dark:bg-paper-dark-badge border border-slate-950/15 dark:border-white/15 px-4 py-1.5 text-xs font-bold text-slate-900 dark:text-amber-300 shadow-xs">
          <span class="inline-block size-2 rounded-full bg-amber-600 dark:bg-amber-400 animate-pulse"></span>
          Get in Touch
        </div>
        <h1 class="text-4xl font-serif font-bold tracking-tight text-slate-950 dark:text-amber-50 sm:text-5xl">
          Let's eliminate scattered document workflows
        </h1>
        <p class="text-base sm:text-lg text-slate-800 dark:text-slate-200 font-sans">
          Ready to transform how your team handles PDFs? Speak with our document intelligence experts today.
        </p>
      </div>

      <!-- MAIN CARD WRAPPER -->
      <div
        class="wow animate__animated animate__fadeInUp grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch bg-paper-light-card dark:bg-paper-dark-card border-2 border-slate-950/15 dark:border-white/15 rounded-[2.5rem] p-6 sm:p-10 shadow-2xl backdrop-blur-md">

        <!-- LEFT INFO PANEL -->
        <div
          class="wow animate__animated animate__fadeInLeft lg:col-span-5 flex flex-col justify-between rounded-[2rem] bg-paper-light dark:bg-paper-dark-preview border border-slate-950/10 dark:border-white/10 p-8"
          data-wow-delay="0.2s">
          <div>
            <h2 class="text-2xl font-serif font-bold text-slate-950 dark:text-amber-50">
              Access your papers with Sporo AI
            </h2>
            <p class="mt-4 text-sm text-slate-800 dark:text-slate-200 leading-relaxed font-sans">
              Bring all your reading materials, research PDFs, and files into one fast, secure interface.
            </p>

            <ul class="mt-8 space-y-4 text-sm font-semibold text-slate-900 dark:text-slate-100 font-sans">
              <li class="flex items-center gap-x-3">
                <span
                  class="flex size-5 items-center justify-center rounded-full bg-paper-light-badge dark:bg-paper-dark-badge text-slate-950 dark:text-amber-300 text-xs font-bold border border-slate-950/10 dark:border-white/10">✓</span>
                Instant multi-thousand page AI summaries
              </li>
              <li class="flex items-center gap-x-3">
                <span
                  class="flex size-5 items-center justify-center rounded-full bg-paper-light-badge dark:bg-paper-dark-badge text-slate-950 dark:text-amber-300 text-xs font-bold border border-slate-950/10 dark:border-white/10">✓</span>
                High-precision OCR text extraction
              </li>
              <li class="flex items-center gap-x-3">
                <span
                  class="flex size-5 items-center justify-center rounded-full bg-paper-light-badge dark:bg-paper-dark-badge text-slate-950 dark:text-amber-300 text-xs font-bold border border-slate-950/10 dark:border-white/10">✓</span>
                Cross-device sync & bank-grade encryption
              </li>
            </ul>
          </div>

          <div class="mt-12 pt-6 border-t border-slate-950/10 dark:border-white/10">
            <p class="text-xs italic text-slate-700 dark:text-slate-300 font-sans">
              "Trusted by thousands of researchers, engineers, and legal teams standardizing document work."
            </p>
          </div>
        </div>

        <!-- RIGHT FORM PANEL -->
        <div class="wow animate__animated animate__fadeInRight lg:col-span-7 flex flex-col justify-center lg:pl-4"
          data-wow-delay="0.3s">
          <form action="#" method="POST" class="space-y-6">

            <div class="grid grid-cols-1 gap-x-6 gap-y-6 sm:grid-cols-2">
              <div>
                <label for="first-name"
                  class="block text-xs font-bold uppercase tracking-wider text-slate-900 dark:text-slate-200 mb-2">
                  First name
                </label>
                <input id="first-name" type="text" name="first-name" autocomplete="given-name"
                  class="block w-full rounded-xl border border-slate-950/20 dark:border-white/20 bg-paper-light dark:bg-paper-dark-badge px-4 py-3 text-sm text-slate-950 dark:text-slate-50 placeholder-slate-500 dark:placeholder-slate-400 focus:outline-hidden focus:border-amber-600 dark:focus:border-amber-400 focus:ring-1 focus:ring-amber-600 dark:focus:ring-amber-400 transition-all" />
              </div>

              <div>
                <label for="last-name"
                  class="block text-xs font-bold uppercase tracking-wider text-slate-900 dark:text-slate-200 mb-2">
                  Last name
                </label>
                <input id="last-name" type="text" name="last-name" autocomplete="family-name"
                  class="block w-full rounded-xl border border-slate-950/20 dark:border-white/20 bg-paper-light dark:bg-paper-dark-badge px-4 py-3 text-sm text-slate-950 dark:text-slate-50 placeholder-slate-500 dark:placeholder-slate-400 focus:outline-hidden focus:border-amber-600 dark:focus:border-amber-400 focus:ring-1 focus:ring-amber-600 dark:focus:ring-amber-400 transition-all" />
              </div>
            </div>

            <div>
              <label for="email"
                class="block text-xs font-bold uppercase tracking-wider text-slate-900 dark:text-slate-200 mb-2">
                Work Email
              </label>
              <input id="email" type="email" name="email" autocomplete="email"
                class="block w-full rounded-xl border border-slate-950/20 dark:border-white/20 bg-paper-light dark:bg-paper-dark-badge px-4 py-3 text-sm text-slate-950 dark:text-slate-50 placeholder-slate-500 dark:placeholder-slate-400 focus:outline-hidden focus:border-amber-600 dark:focus:border-amber-400 focus:ring-1 focus:ring-amber-600 dark:focus:ring-amber-400 transition-all" />
            </div>

            <div>
              <label for="company"
                class="block text-xs font-bold uppercase tracking-wider text-slate-900 dark:text-slate-200 mb-2">
                Company / Organization
              </label>
              <input id="company" type="text" name="company" autocomplete="organization"
                class="block w-full rounded-xl border border-slate-950/20 dark:border-white/20 bg-paper-light dark:bg-paper-dark-badge px-4 py-3 text-sm text-slate-950 dark:text-slate-50 placeholder-slate-500 dark:placeholder-slate-400 focus:outline-hidden focus:border-amber-600 dark:focus:border-amber-400 focus:ring-1 focus:ring-amber-600 dark:focus:ring-amber-400 transition-all" />
            </div>

            <div>
              <label for="message"
                class="block text-xs font-bold uppercase tracking-wider text-slate-900 dark:text-slate-200 mb-2">
                How can we help?
              </label>
              <textarea id="message" name="message" rows="3"
                class="block w-full rounded-xl border border-slate-950/20 dark:border-white/20 bg-paper-light dark:bg-paper-dark-badge px-4 py-3 text-sm text-slate-950 dark:text-slate-50 placeholder-slate-500 dark:placeholder-slate-400 focus:outline-hidden focus:border-amber-600 dark:focus:border-amber-400 focus:ring-1 focus:ring-amber-600 dark:focus:ring-amber-400 transition-all"></textarea>
            </div>

            <div class="flex items-center gap-x-3">
              <input id="agree-to-policies" type="checkbox" name="agree-to-policies"
                class="size-4 rounded-md border-slate-950/30 dark:border-white/30 text-amber-600 dark:text-amber-400 focus:ring-amber-500 bg-paper-light dark:bg-paper-dark-badge cursor-pointer" />
              <label for="agree-to-policies" class="text-xs text-slate-800 dark:text-slate-200 font-sans">
                I agree to the <a href="#"
                  class="underline font-bold text-slate-950 dark:text-amber-300 hover:text-amber-700 dark:hover:text-amber-200">privacy
                  policy</a> and processing of personal data.
              </label>
            </div>

            <button type="submit"
              class="w-full rounded-2xl bg-slate-950 dark:bg-paper-accent-dark px-6 py-3.5 text-center text-sm font-bold text-white dark:text-slate-950 border border-slate-950 dark:border-amber-300/40 shadow-md hover:scale-[1.02] transition-all duration-200 cursor-pointer">
              Book a demo
            </button>

          </form>
        </div>

      </div>

    </div>
  </div>
</template>