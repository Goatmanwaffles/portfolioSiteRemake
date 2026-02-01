<script lang='ts'>
     import NavBar from '$lib/nav.svelte';
     import placeholder from '$lib/assets/1.jpg'
</script>


<div class="bg-gray-800 h-screen w-full overflow-hidden">
     <NavBar/>
     <div class="flex flex-col mt-1/3">
          
     <div class="flex items-center justify-center mt-32">
          <h1 class="text-white text-5xl font-bold">About me</h1>
     </div>
     <div class="grid grid-cols-2 ml-32 mr-32">
     <div class="ml-32">
          <p class="text-white text-xl">Hello! I'm Logan, a professional developer and student at Kent State University. I am currently studying Computer Science as a sophmore, with a focus in software and web development.</p>
     </div>
     <div>
          <img class="h-96 w-96 object-contain" src={placeholder} alt="">
     </div>
     </div>
     <div class="flex items-center flex-col w-full mt-32">
          <h2 class="text-pink-500 text-4xl justify-center self-auto font-bold">My</h2>
          <div class="grid grid-cols-3 gap-32 ml-32 mr-32 justify-center self-center w-full items-center text-center mt-8">
               <div class="flex flex-col">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Past</h3>
                    <p class="text-white">Ever since I was a kid I have been interesed in computers</p>
               </div>
               <div class="flex flex-col">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Present</h3>
                    <p class="text-white">Currently attending Kent State for CS</p>
               </div>
               <div class="flex flex-col">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Future</h3>
                    <p class="text-white">Looking for a job</p>
               </div>
          </div>
     </div>
</div>
</div>