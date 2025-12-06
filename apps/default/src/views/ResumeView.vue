<script setup lang="ts">
// No script logic needed for this static layout
</script>

<template>
  <div class="min-h-screen bg-white font-sans flex flex-col lg:flex-row">
    <!-- Sidebar -->
    <aside class="w-full lg:w-1/3 bg-[#154c43] text-white p-8 lg:min-h-screen flex flex-col">
      <!-- Profile Header -->
      <div class="flex flex-col items-center mb-12 text-center">
        <div class="w-32 h-32 rounded-full overflow-hidden mb-6 border-4 border-[#2a665b]">
          <!-- Using a placeholder image since we don't have the specific asset, user can replace -->
          <img src="https://placehold.co/400x400/2a665b/white?text=RT" alt="Rick Tang" class="w-full h-full object-cover">
        </div>
        <h1 class="text-3xl font-bold mb-1">Lee Weiquan</h1>
        <p class="text-gray-300 text-lg">Backend Web Developer</p>
      </div>

      <!-- Details -->
      <div class="mb-10">
        <h2 class="text-xl font-bold mb-4 border-b border-[#2a665b] pb-2">Details</h2>
        <div class="space-y-4 text-sm">
          <div>
            <h3 class="font-bold text-gray-200">Address</h3>
            <p class="text-gray-300">Butterworth, Malaysia</p>
          </div>
          <div>
            <h3 class="font-bold text-gray-200">Phone</h3>
            <p class="text-gray-300">014-3076093</p>
          </div>
          <div>
            <h3 class="font-bold text-gray-200">Email</h3>
            <a href="mailto:franklee809@gmail.com" class="text-gray-300 hover:text-white">franklee809@gmail.com</a>
          </div>
        </div>
      </div>

      <!-- Links -->
      <div class="mb-10">
        <h2 class="text-xl font-bold mb-4 border-b border-[#2a665b] pb-2">Links</h2>
        <div class="flex flex-col space-y-2 text-sm">
          <a href="https://www.linkedin.com/in/lee-weiquan-13b500164/" target="_blank" class="text-gray-300 hover:text-white underline decoration-[#2a665b] underline-offset-4">LinkedIn</a>
          <!-- <a href="#" class="text-gray-300 hover:text-white underline decoration-[#2a665b] underline-offset-4">Dribbble</a> -->
          <!-- <a href="#" class="text-gray-300 hover:text-white underline decoration-[#2a665b] underline-offset-4">Behance</a> -->
        </div>
      </div>

      <!-- Skills -->
      <div class="mb-8">
        <h2 class="text-xl font-bold mb-6 border-b border-[#2a665b] pb-2">Skills</h2>
        <div class="space-y-4">
          <!-- Skill Items -->
          <div>
            <div class="flex justify-between mb-1">
              <span class="text-sm">Laravel</span>
            </div>
            <div class="w-full bg-[#0e332d] h-1.5 rounded-full overflow-hidden">
              <div class="bg-white h-1.5 rounded-full" style="width: 95%"></div>
            </div>
          </div>
          
          <div>
            <div class="flex justify-between mb-1">
              <span class="text-sm">Node.js</span>
            </div>
            <div class="w-full bg-[#0e332d] h-1.5 rounded-full overflow-hidden">
              <div class="bg-white h-1.5 rounded-full" style="width: 90%"></div>
            </div>
          </div>

          <div>
            <div class="flex justify-between mb-1">
              <span class="text-sm">Vue.js</span>
            </div>
            <div class="w-full bg-[#0e332d] h-1.5 rounded-full overflow-hidden">
              <div class="bg-white h-1.5 rounded-full" style="width: 90%"></div>
            </div>
          </div>

          <div>
            <div class="flex justify-between mb-1">
              <span class="text-sm">Kubernetes & Docker</span>
            </div>
            <div class="w-full bg-[#0e332d] h-1.5 rounded-full overflow-hidden">
              <div class="bg-white h-1.5 rounded-full" style="width: 85%"></div>
            </div>
          </div>

          <div>
            <div class="flex justify-between mb-1">
              <span class="text-sm">Cloud (Alibaba/Huawei)</span>
            </div>
            <div class="w-full bg-[#0e332d] h-1.5 rounded-full overflow-hidden">
              <div class="bg-white h-1.5 rounded-full" style="width: 80%"></div>
            </div>
          </div>

        </div>
      </div>
    </aside>

    <!-- Main Content -->
    <main class="w-full lg:w-2/3 p-8 lg:p-16 text-gray-800">
      
      <!-- Profile -->
      <section class="mb-12">
        <h2 class="text-2xl font-bold mb-6 text-black">Profile</h2>
        <p class="text-gray-600 leading-relaxed max-w-2xl">
          Aspiring Backend Developer eager to advance expertise in web technologies within a prestigious IT company. Committed to contributing to and learning from high-level projects that enhance skills and drive technological innovations.
        </p>
      </section>

      <!-- Experience -->
      <section class="mb-12">
        <h2 class="text-2xl font-bold mb-8 text-black">Experience</h2>
        
        <div class="space-y-8">
          <!-- Job 1 -->
          <div>
            <div class="flex flex-col sm:flex-row justify-between sm:items-baseline mb-2">
              <div>
                <h3 class="font-bold text-lg text-black">TOGL Technology Sdn.Bhd</h3>
                <div class="text-gray-700">Backend Web Developer</div>
              </div>
              <div class="text-sm text-gray-500">04/2020 – Current</div>
            </div>
            <ul class="list-disc list-outside ml-4 text-gray-600 space-y-1 mt-2 text-sm">
              <li>Championed the development of a high-traffic e-commerce platform using Laravel, Node.js, and Nuxt.js.</li>
              <li>Engineered robust cloud solutions leveraging Alibaba Cloud and Huawei Cloud; specialized in container orchestration using Kubernetes.</li>
              <li>Enhanced system security and performance by implementing load balancing, effective caching strategies, and database optimization.</li>
              <li>Led initiatives to refine codebase adhering to SOLID principles and clean code practices.</li>
              <li>Developed an AI chatbot using RAG architecture hosted on DigitalOcean.</li>
            </ul>
          </div>

          <!-- Job 2 -->
          <div>
            <div class="flex flex-col sm:flex-row justify-between sm:items-baseline mb-2">
              <div>
                <h3 class="font-bold text-lg text-black">Tinnolab Sdn.bhd</h3>
                <div class="text-gray-700">Web Developer (Part Time)</div>
              </div>
              <div class="text-sm text-gray-500">01/2019 – 03/2020</div>
            </div>
            <ul class="list-disc list-outside ml-4 text-gray-600 space-y-1 mt-2 text-sm">
              <li>Overhauled an existing e-commerce system, transitioning to Laravel and integrating Vue.js and Vuetify.</li>
              <li>Created a comprehensive new ordering system with detailed admin and merchant panels.</li>
              <li>Facilitated financial transactions by integrating multiple payment gateways.</li>
            </ul>
          </div>

          <!-- Job 3 -->
          <div>
            <div class="flex flex-col sm:flex-row justify-between sm:items-baseline mb-2">
              <div>
                <h3 class="font-bold text-lg text-black">Tinnolab Sdn.bhd</h3>
                <div class="text-gray-700">Web Developer (Intern)</div>
              </div>
              <div class="text-sm text-gray-500">08/2018 – 12/2018</div>
            </div>
            <ul class="list-disc list-outside ml-4 text-gray-600 space-y-1 mt-2 text-sm">
              <li>Supported the maintenance of an e-commerce system, optimizing existing code using ThinkPHP, Bootstrap, and JQuery.</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- Education -->
      <section class="mb-12">
        <h2 class="text-2xl font-bold mb-6 text-black">Education</h2>
        <div>
          <h3 class="font-bold text-lg text-black">Coventry University</h3>
          <p class="text-gray-600 mt-1">Degree in Computer Science, 04/2017 – 04/2020</p>
          <p class="text-gray-500 text-sm">CGPA: 3.5 / 4.00</p>
        </div>
        <div class="mt-4">
          <h3 class="font-bold text-lg text-black">INTI International College Penang</h3>
          <p class="text-gray-600 mt-1">Foundation in Business & IT, 04/2016 – 03/2017</p>
          <p class="text-gray-500 text-sm">CGPA: 2.99 / 4.00</p>
        </div>
      </section>

      <!-- Languages -->
      <section>
        <h2 class="text-2xl font-bold mb-6 text-black">Languages</h2>
        <div class="space-y-1">
          <p class="text-gray-600">English</p>
          <p class="text-gray-600">Mandarin</p>
          <p class="text-gray-600">Malay</p>
        </div>
      </section>

    </main>
  </div>
</template>

<style scoped>
/* Any specific overrides if tailwind isn't enough, but tailwind should handle it */
</style>
