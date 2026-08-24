<template>
  <div class="relative min-h-screen bg-[#0b0f19] flex items-center justify-center overflow-hidden font-sans">

    <!-- Beautiful glowing background blobs -->
    <div
      class="absolute top-1/4 left-1/4 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-indigo-600/20 rounded-full blur-[120px] pointer-events-none">
    </div>
    <div
      class="absolute bottom-1/4 right-1/4 translate-x-1/2 translate-y-1/2 w-96 h-96 bg-purple-600/15 rounded-full blur-[120px] pointer-events-none">
    </div>

    <!-- Main Content Container -->
    <main class="relative z-10 w-full max-w-2xl mx-auto px-6 text-center">

      <!-- Large beautiful 404 text with a gradient glow -->
      <div class="relative inline-block select-none">
        <span
          class="absolute inset-0 text-[10rem] font-extrabold text-indigo-500/10 blur-xl tracking-tighter sm:text-[14rem]">404</span>
        <h1
          class="text-[10rem] font-extrabold tracking-tighter bg-clip-text text-transparent bg-gradient-to-b from-white via-indigo-200 to-indigo-500 sm:text-[14rem] leading-none">
          404
        </h1>
      </div>

      <!-- Error Message -->
      <div class="mt-4">
        <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">
          Lost in the deep dark?
        </h2>
        <p class="mt-4 text-base leading-7 text-gray-400 max-w-md mx-auto">
          The page you are looking for has drifted out of reach. Let's get you back to familiar coordinates.
        </p>
      </div>

      <!-- Action Buttons -->
      <div class="mt-10 flex flex-col sm:flex-row items-center justify-center gap-4">
        <NuxtLink to="/"
          class="w-full sm:w-auto px-6 py-3 rounded-xl bg-indigo-500 text-sm font-semibold text-white shadow-[0_4px_20px_rgba(99,102,241,0.4)] hover:bg-indigo-400 hover:shadow-[0_4px_25px_rgba(99,102,241,0.6)] transition-all duration-300 ease-in-out transform hover:-translate-y-0.5 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500">
          Go back home
        </NuxtLink>

        <NuxtLink to="/contact"
          class="w-full sm:w-auto px-6 py-3 rounded-xl bg-white/5 border border-white/10 text-sm font-semibold text-gray-300 hover:bg-white/10 hover:text-white hover:border-white/20 transition-all duration-300 ease-in-out backdrop-blur-sm">
          Contact support <span aria-hidden="true"
            class="ml-1 inline-block transition-transform duration-200 group-hover:translate-x-1">&rarr;</span>
        </NuxtLink>
      </div>

    </main>

    <!-- Subtle futuristic grid line on the bottom -->
    <div
      class="absolute bottom-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-indigo-500/20 to-transparent">
    </div>
  </div>
</template>