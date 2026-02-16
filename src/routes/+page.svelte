<script lang="ts">
  import Orbit from '$lib/orbit.svelte';
  import NavBar from '$lib/nav.svelte';
</script>

<div class="bg-gray-800 h-screen w-full relative overflow-hidden">
  <Orbit />
  <div class="relative z-20 flex flex-col items-center justify-center gap-6 h-screen w-full">
    <h1 class="text-5xl font-bold text-pink-500 col-span-2">Logan Senol</h1>
    <p class="text-gray-400 text-xl font-bold">A Full Stack Developer</p>
    <div class="flex md:flex-row gap-32 flex-col">
      <div class="group relative rounded-full overflow-hidden">
        <span class="pointer-events-none absolute inset-0 bg-gradient-to-r from-transparent via-white/40 to-transparent -translate-x-full opacity-0 group-hover:animate-flash z-20"></span>
        <a href="/about" class="relative inline-block rounded-full bg-pink-400 px-14 py-2 hover:bg-pink-600 transition-colors duration-500 z-10">&lt;About Me&gt;</a>
      </div>
      <div class="group relative rounded-full overflow-hidden">
        <span class="pointer-events-none absolute inset-0 bg-gradient-to-r from-transparent via-white/40 to-transparent -translate-x-full opacity-0 group-hover:animate-flash z-20"></span>
        <a href="/projects" class="relative inline-block rounded-full bg-pink-400 px-14 py-2 hover:bg-pink-600 transition-colors duration-1000 z-10">&lt;My Projects&gt;</a>
      </div>
    </div>
  </div>
</div>