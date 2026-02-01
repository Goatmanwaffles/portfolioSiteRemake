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
</script>

<nav class="fixed w-full h-1/8 z-40" id="navbar">
     <div class="flex flex-row w-1/3 bg-stone-50 rounded-full justify-self-center justify-center align-center h-1/3 transition-all duration-700"
     class:scrolled
     style="width: {scrolled ? 'min(50%)' : '100%'}; 
     opacity: {scrolled ? '0.45' : '0.75'}; 
     border-radius: { scrolled ? '9999px' : '0%'}; 
     margin-top: { scrolled ? '25px' : '0'}">

          <div class="grid grid-cols-3 gap-8 mt-auto mb-auto">
               <a href="/about">About Me</a>
               <a href="/">Home</a>
               <a href="/projects">Projects</a>
          </div>
     </div>
</nav>