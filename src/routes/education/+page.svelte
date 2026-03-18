<script lang="ts">
    import NavBar from '$lib/nav.svelte';
    import placeholder from '$lib/assets/1.jpg'
    import SteamSpecImg from '$lib/assets/SteamSpectiveExample.png'
    import WIPIMG from '$lib/assets/WIP.png'
</script>

<div class="bg-gray-800 min-h-screen w-full">
    <NavBar/>
    <div class="flex flex-col mt-1/3 ml-16 mr-16">
        <div class="flex items-center justify-center mt-32">
            <h1 class = "text-white text-5xl font-bold font-sans">My Education</h1>
        </div>

        <div class="space-y-8 mt-8">

            <!-- Education Cards -->
            <div class="flex flex-col gap-8">

                <div class="bg-gray-700 p-8 rounded-lg shadow-lg lg:max-h-60 transition delay-0 duration-250 ease-in-out hover:translate-y-2 hover:scale-105 hover:bg-gray-600">
                    <div class="grid grid-rows-2 lg:grid-cols-2 gap-8">
                        <div>
                              <h3 class="font-bold text-pink-400 text-2xl">Kent State University</h3>
                              <p class="font-light text-gray-400">August 2024 - May 2027</p>
                              <p class="font-light text-gray-400">B.S. Computer Science</p>
                              <h3 class="font-semibold text-pink-400 text-lg">Relevant Course Work:</h3>
                              <p class="text-gray-300">CS 1, CS 2, CS 3, Discrete Math, Statistics (Using R), Operating Systems, Computer Networks, Computer Architecture, Database Systems</p>
                        </div>
                        <p class="ml-auto font-light text-gray-400">GPA:3.7</p>
                    </div>
                </div>

                <div class="bg-gray-700 p-8 rounded-lg shadow-lg lg:max-h-60 transition delay-0 duration-250 ease-in-out hover:translate-y-2 hover:scale-105 hover:bg-gray-600">
                    <div class="grid grid-rows-2 lg:grid-cols-2 gap-8">
                        <div>
                              <h3 class="font-bold text-pink-400 text-2xl">Lakeland Community College</h3>
                              <p class="font-light text-gray-400">August 2022 - May 2024</p>
                              <p class="font-light text-gray-400">Associates of Science</p>
                              <h3 class="font-semibold text-pink-400 text-lg">Relevant Course Work:</h3>
                              <p class="text-gray-300">Intro to Python, Intro Computer Programming, Intro to SQL databases</p>
                        </div>
                        <p class="ml-auto font-light text-gray-400">GPA:3.2</p>
                    </div>
                </div>
        </div>

    </div>
</div>
</div>