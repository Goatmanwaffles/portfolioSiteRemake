<script lang='ts'>
     import NavBar from '$lib/nav.svelte';
     import logan from '$lib/assets/Logan.jpg'
</script>


<div class="bg-gray-800 h-fill w-full">
     <NavBar/>
     <div class="flex flex-col ml-4 mr-4 lg:ml-16 lg:mr-16 py-16">
     <div class="space-y-12 text-center max-w-4xl mx-auto px-4 sm:px-0 py-2"> 
          <h1 class="text-white text-5xl font-bold font-sans">About Me</h1>
          <p class="text-white text-xl">Hello! I'm Logan, a professional developer and student at Kent State University. I am currently studying Computer Science as a sophmore, with a focus in software and web development.</p>
          <img class="h-96 w-96 object-contain" src={logan} alt="">
     </div>
     </div>

     <div class="flex items-center flex-col w-full mt-32">
          <h2 class="text-pink-500 text-4xl justify-center self-auto font-bold">My</h2>
          <div class="grid grid-rows-3 lg:grid-rows-1 lg:grid-cols-3 gap-16 justify-center self-center text-center mt-8">
               <div class="bg-gray-700 p-8 rounded-lg shadow-lg">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Past</h3>
                    <p class="text-white justify-center">Ever since I was a kid I have been interesed in computers. My parents bought me my first PC for my 10th birthday and ever since then I have been interested in programming and the technology behind computers. Young me loved to play RTS and factory builder games which gave me the kick I needed for making things. I loved to take programming classes in middle school, making over the top class projects to try and learn more. I also had various failed ventures into game programming with my friends during our lunch periods, making pygame projects before any of us knew what a game engine was.</p>
               </div>
               <div class="bg-gray-700 p-8 rounded-lg shadow-lg">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Present</h3>
                    <p class="text-white">I am currently attending Kent State University, studying for my Bachelors of Science in Computer Science. I am a second year student, graduating in May of 2027 or December 2028. Outside of school I work as a shift lead at a local retail chain and have been contributing to the University's Computer Science club <a class="text-decoration-line: underline" href="https://hacksu.com/">HacKSU</a> in a leadership role. I have also been focusing on my own development skills, developing my own <a class="text-decoration-line: underline" href="./projects">Projects</a> and searching for internship opprotunities to grow as a professional.</p>
               </div>
               <div class="bg-gray-700 p-8 rounded-lg shadow-lg">
                    <h3 class="justify-center text-3xl font-semibold text-pink-500">Future</h3>
                    <p class="text-white">In the near future, I aim to complete my degree and secure a position in the tech industry. I am currently seeking software or web development roles, but I am open to exploring any opportunity within the field. My goal is to become a well-rounded developer who contributes to real-world, scalable, and impactful products that make a difference. I am continuously expanding my technical skill set, with a growing interest in AI integration, development tools, and computer networking systems. Motivated by the challenges of this ever-changing industry, I strive to learn, adapt, and improve every day.</p>
               </div>
          </div>
     </div>

     <!-- Experience Section Cards-->
      <div class="mt-32 px-16 pb-16">
          <h2 class="text-pink-500 text-4xl justify-center self-auto font-bold text-center">Experience</h2>

          <div class="space-y-8 mt-8">
               <div class="bg-gray-700 p-8 rounded-lg shadow-lg ">
                    <h3 class="justify-center text-2xl font-bold text-pink-500">Shift Lead</h3>
                    <p class="font-light text-gray-400">Heinen's Grocery Store</p>
                    <p class="font-light text-gray-400">2023-Present</p>
                    <ul class="text-white list-outside list-disc space-y-2 font-base">
                         <li>Lead a team of 20+ retail associates, performing front end duties and ensuring smooth store operations.</li>
                         <li>Consistently exceeded customer expectations through professional and empathetic interactions, handling refunds, outreach, and issue resolution to ensure customer satisfaction.</li>
                         <li>Managed scheduling and task delegation through high pressure environments, ensuring smooth workflow and proper staff management.</li>
                    </ul>
               </div>
          </div>

          <div class="space-y-8 mt-8">
               <div class="bg-gray-700 p-8 rounded-lg shadow-lg">
                    <h3 class="justify-center text-2xl font-bold text-pink-500">Software Developer Intern</h3>
                    <p class="font-light text-gray-400">All Around Children Child Care</p>
                    <p class="font-light text-gray-400">2025-Present</p>
                    <ul class="text-white list-outside list-disc space-y-2 font-base">
                         <li>Developed a react based data management app for internal buissness use.</li>
                         <li>Aggregated and normalized multiple sources of data together into dashboard systems, improving visibility and team efficiency.</li>
                         <li>Designed and implemented a company-wide scoring system allowing administrators to rank branch centers and quickly identify performance gaps.</li>
                    </ul>
               </div>
          </div>

          <div class="space-y-8 mt-8 flex flex-col justify-center">
               <h2 class="text-pink-500 text-4xl justify-center self-auto font-bold text-center">Want to learn more?</h2>
               <a href="/resume.pdf" download class="bg-gradient-to-r from-pink-500 to-pink-400 text-white text-center font-bold text-xl py-5 px-12 rounded-xl shadow-xl hover:from-pink-600 hover:to-pink-500 hover:scale-105 transition transform duration-300">My Resume</a>
          </div>
          
      </div>
</div>