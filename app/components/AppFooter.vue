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
    <footer class="w-full pb-12 pt-8 px-4 sm:px-6 lg:px-8">
        <div class="mx-auto max-w-6xl space-y-8">

            <!-- TOP CTA BANNER -->
            <div
                class="wow animate__animated animate__fadeInUp relative overflow-hidden rounded-[2.5rem] bg-slate-950 dark:bg-paper-dark-card px-6 py-16 text-center shadow-2xl border-2 border-slate-950/15 dark:border-white/15">

                <!-- Subtle Background Glow -->
                <div
                    class="pointer-events-none absolute inset-0 bg-[radial-gradient(circle_at_top,_var(--tw-gradient-stops))] from-amber-500/10 via-transparent to-transparent">
                </div>

                <div class="relative z-10 mx-auto max-w-2xl space-y-6">
                    <h2 class="text-2xl sm:text-3xl font-serif font-bold tracking-tight text-white dark:text-amber-50">
                        Join thousands of professionals simplifying their document workflows today.
                    </h2>
                    <div>
                        <NuxtLink to="/contact"
                            class="inline-flex items-center justify-center rounded-2xl bg-paper-light dark:bg-paper-accent-dark px-7 py-3.5 text-sm font-bold text-slate-950 border border-slate-950 dark:border-amber-300/40 shadow-lg hover:scale-105 transition-all duration-200">
                            Start for free
                        </NuxtLink>
                    </div>
                </div>
            </div>

            <!-- MAIN FOOTER FLOATING CARD -->
            <div class="wow animate__animated animate__fadeInUp rounded-[2.5rem] border-2 border-slate-950/15 dark:border-white/15 bg-paper-light-card dark:bg-paper-dark-card p-8 sm:p-12 backdrop-blur-md shadow-xl"
                data-wow-delay="0.1s">
                <div class="grid grid-cols-1 gap-10 lg:grid-cols-12 lg:gap-8">

                    <!-- BRAND COLUMN -->
                    <div class="lg:col-span-5 space-y-6">
                        <NuxtLink to="/" class="flex items-center gap-x-2.5">
                            <div
                                class="flex size-8 items-center justify-center rounded-xl bg-slate-950 dark:bg-paper-accent-dark font-black text-white dark:text-slate-950 text-base shadow-xs">
                                S
                            </div>
                            <span class="text-lg font-serif font-bold tracking-wide text-slate-950 dark:text-amber-50">
                                SPORO AI
                            </span>
                        </NuxtLink>

                        <p
                            class="max-w-sm text-xs sm:text-sm text-slate-800 dark:text-slate-200 leading-relaxed font-sans">
                            Sporo AI empowers researchers, legal experts, and teams to turn massive document libraries
                            into clear, structured insights in seconds.
                        </p>

                        <!-- SOCIAL LINKS -->
                        <div class="flex items-center gap-x-4 text-slate-700 dark:text-slate-300">
                            <a href="#" class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors"
                                aria-label="X (Twitter)">
                                <svg class="size-4" fill="currentColor" viewBox="0 0 24 24">
                                    <path
                                        d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z" />
                                </svg>
                            </a>
                            <a href="#" class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors"
                                aria-label="Instagram">
                                <svg class="size-4" fill="none" stroke="currentColor" stroke-width="2"
                                    viewBox="0 0 24 24">
                                    <rect width="20" height="20" x="2" y="2" rx="5" ry="5" />
                                    <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" />
                                    <line x1="17.5" x2="17.51" y1="6.5" y2="6.5" />
                                </svg>
                            </a>
                            <a href="#" class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors"
                                aria-label="LinkedIn">
                                <svg class="size-4" fill="currentColor" viewBox="0 0 24 24">
                                    <path
                                        d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.46 10.9v8.37H9.25V10.9H6.46M7.86 6.7a1.62 1.62 0 1 0 0 3.24 1.62 1.62 0 0 0 0-3.24z" />
                                </svg>
                            </a>
                            <a href="#" class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors"
                                aria-label="GitHub">
                                <svg class="size-4" fill="currentColor" viewBox="0 0 24 24">
                                    <path
                                        d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
                                </svg>
                            </a>
                        </div>
                    </div>

                    <!-- LINKS COLUMNS -->
                    <div class="grid grid-cols-3 gap-6 sm:gap-8 lg:col-span-7">
                        <!-- Product -->
                        <div>
                            <h3 class="text-xs font-bold uppercase tracking-wider text-slate-950 dark:text-amber-50">
                                Product
                            </h3>
                            <ul
                                class="mt-4 space-y-2.5 text-xs sm:text-sm text-slate-800 dark:text-slate-300 font-sans">
                                <li>
                                    <NuxtLink to="/features"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">
                                        Features</NuxtLink>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Pricing</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Integrations</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Changelog</a>
                                </li>
                            </ul>
                        </div>

                        <!-- Resources -->
                        <div>
                            <h3 class="text-xs font-bold uppercase tracking-wider text-slate-950 dark:text-amber-50">
                                Resources
                            </h3>
                            <ul
                                class="mt-4 space-y-2.5 text-xs sm:text-sm text-slate-800 dark:text-slate-300 font-sans">
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Documentation</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Tutorials</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Blog</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Support</a>
                                </li>
                            </ul>
                        </div>

                        <!-- Company -->
                        <div>
                            <h3 class="text-xs font-bold uppercase tracking-wider text-slate-950 dark:text-amber-50">
                                Company
                            </h3>
                            <ul
                                class="mt-4 space-y-2.5 text-xs sm:text-sm text-slate-800 dark:text-slate-300 font-sans">
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">About</a>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Careers</a>
                                </li>
                                <li>
                                    <NuxtLink to="/contact"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Contact
                                    </NuxtLink>
                                </li>
                                <li><a href="#"
                                        class="hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Partners</a>
                                </li>
                            </ul>
                        </div>
                    </div>

                </div>

                <!-- BOTTOM DIVIDER & COPYRIGHT -->
                <div
                    class="mt-12 pt-6 border-t border-slate-950/10 dark:border-white/10 flex flex-col sm:flex-row items-center justify-between gap-y-4 text-xs text-slate-700 dark:text-slate-300 font-sans">
                    <p>© 2026 Sporo AI. All rights reserved.</p>

                    <div class="flex items-center gap-2">
                        <a href="#"
                            class="underline underline-offset-4 hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Privacy
                            Policy</a>
                        <a href="#"
                            class="underline underline-offset-4 hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Terms
                            of Service</a>
                        <a href="#"
                            class="underline underline-offset-4 hover:text-amber-600 dark:hover:text-amber-300 transition-colors">Cookies
                            Settings</a>
                    </div>
                </div>
            </div>

        </div>
    </footer>
</template>