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
            <h1 class = "text-white text-5xl font-bold font-sans">Check out what I've made!</h1>
        </div>

        <div class="space-y-8 mt-8">
            <h2 class="text-pink-500 font-bold text-4xl">Projects</h2>

            <!-- Project Cards -->
            <div class="grid grid-rows-2 lg:grid-cols-2 gap-8">

                <div class="bg-gray-700 p-8 rounded-lg shadow-lg lg:max-h-60 transition delay-0 duration-250 ease-in-out hover:translate-y-2 hover:scale-105 hover:bg-gray-600">
                    <div class="grid grid-rows-2 lg:grid-cols-2 gap-8">
                        <div>
                            <h3 class="font-bold text-pink-400 text-2xl">SteamSpective</h3>
                            <p class="font-light text-gray-400">A react based Steam stats higher or lower game</p>
                            <p class="text-white max-h-5/10">Created using React, NodeJS, and the Steam Web API</p>
                        </div>
                        <div>
                            <img class="h-auto w-full object-contain object-center" src={SteamSpecImg} alt="">
                        </div>
                    </div>
                </div>

                <div class="bg-gray-700 p-8 rounded-lg shadow-lg lg:max-h-60 transition delay-0 duration-250 ease-in-out hover:translate-y-2 hover:scale-105 hover:bg-gray-600">
                    <div class="grid grid-rows-2 lg:grid-cols-2 gap-8">
                        <div>
                            <h3 class="font-bold text-pink-400 text-2xl">Meal Prep Assistant</h3>
                            <p class="font-light text-gray-400">An app to help track my meal prep</p>
                            <p class="text-white max-h-5/10">Created using Svelte, PostgresSQL, Typescript</p>
                        </div>
                        <div>
                            <img class="h-auto w-full object-contain object-center scale-80" src={WIPIMG} alt="">
                        </div>
                    </div>
                </div>
        </div>

    </div>
</div>
</div>