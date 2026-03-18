<script lang="ts">
  import { onMount } from "svelte";
     let scrolled = $state(false);
     //Store nav Links as items for ease of addition or subtraction
     const navLinks = [
          {href: "/", label: "Home Page"},
          {href: "/about", label: "About Me"},
          {href: "/projects", label: "My Projects"}
     ];

     //Mount scroll detection
     onMount(() =>{
          const detectScroll = () => {
               scrolled = window.scrollY > 125;
          }
          const navbar = document.getElementById("navbar")
          window.addEventListener("scroll", detectScroll);
          
          return () => removeEventListener("scroll", detectScroll);
     });

     let menuOpen = $state(false);
</script>

<nav class="fixed w-full z-40" id="navbar">
     <div 
     class="mx-auto bg-stone-50 transition-all duration-500 flex items-center md:mx-auto w-full md:justify-center
           w-12 h-12  justify-center"
     class:scrolled
     style="
     opacity: {scrolled ? '0.45' : '0.75'}; 
     margin-top: { scrolled ? '25px' : '0'};
     border-radius: { scrolled ? '9999px': '0'};
     width: { scrolled ? '33%': 'fill'}"
     >

          <!-- Desktop Links -->
          <div class="hidden lg:grid grid-cols-5 gap-4 font-bold text-center">
               <a class="nav-link" href="/about">About Me</a>
               <a class="nav-link" href="/projects">Projects</a>
               <a class="nav-link" href="/">Home</a>
               <a class="nav-link" href="/education">Education</a>
               <a class="nav-link" href="/contact">Contact Me</a>
          </div>

          <!-- Mobile Hamburger Menu -->
          <button
               class="lg:hidden w-12 h-12 rounded-full flex items-center justify-center font-bold"
               onclick={() => menuOpen = !menuOpen}
               aria-label="Toggle Menu"
          >
          ☰
          </button>

     </div>

     <!-- Mobile Drop Menu -->
      {#if menuOpen}
     <div class="lg:hidden mt-3 w-full bg-stone-50 rounded-xl shadow-lg py-4 text-center space-y-3 justify-center">
      <a class="block nav-link" href="/about" onclick={() => menuOpen = false}>About Me</a>
      <a class="block nav-link" href="/" onclick={() => menuOpen = false}>Home</a>
      <a class="block nav-link" href="/projects" onclick={() => menuOpen = false}>Projects</a>
     </div>
     {/if}

</nav>
