<script>
     import NavBar from '$lib/nav.svelte';
</script>

<div class="bg-gray-800 min-h-screen w-full">
<NavBar/>
<div class="flex flex-col mt-1/3 ml-16 mr-16">
     <div class="flex items-center justify-center mt-32">
          <h1 class = "text-white text-5xl font-bold font-sans">Contact Me!</h1>
     </div>
     <div class="grid grid-cols-3 gap-8 mt-4">
          <div class="bg-gray-700 p-8 rounded-lg shadow-lg lg:max-h-80">
               <h3 class="flex justify-center text-white font-bold text-3xl">My Socials</h3>
               <div class="flex flex-col gap-4 justify-items-center">
                    <a class="justify-center text-blue-400 flex text-lg font-semibold" href="https://www.linkedin.com/in/logan-senol/">LinkedIn</a>
                    <a class="justify-center text-blue-400 flex text-lg font-semibold" href="https://github.com/Goatmanwaffles">Github</a>
                    <a class="justify-center text-blue-400 flex text-lg font-semibold" href="https://discord.gg/Yvmfyzp2">Discord</a>
                    <a class="justify-center text-blue-400 flex text-lg font-semibold" href="https://devpost.com/Goatmanwaffles?ref_content=user-portfolio&ref_feature=portfolio&ref_medium=global-nav">DevPost</a>
               </div>
          </div>
          <div class="bg-gray-700 p-8 rounded-lg shadow-lg col-span-2">
               <h3 class="flex justify-center text-white font-bold text-3xl">Send Me a Message!</h3>
               <form action="#" class="space-y-8">
          <div>
              <label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Your email</label>
              <input type="email" id="email" class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" placeholder="Email" required>
          </div>
          <div>
              <label for="subject" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Subject</label>
              <input type="text" id="subject" class="block p-3 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" placeholder="Subject" required>
          </div>
          <div class="sm:col-span-2">
              <label for="message" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Your message</label>
              <textarea id="message" rows="6" class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="Leave a comment..."></textarea>
          </div>
          <button type="submit" class="py-3 px-5 text-sm font-medium text-center text-white rounded-lg bg-primary-700 sm:w-fit hover:bg-primary-800 focus:ring-4 focus:outline-none focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800">Send message</button>
      </form>
          </div>
     </div>
</div>
</div>