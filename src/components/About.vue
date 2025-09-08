<script setup lang="ts">
import TitleSection from '@/components/TitleSection.vue';
import { Button } from "@/components/ui/button";
import { DownloadIcon } from 'lucide-vue-next';
</script>

<template>
    <TitleSection title="About Me"/>
    <section class="text-base text-gray-600 md:text-left grid grid-cols-1 md:grid-cols-3 gap-6">       

			<div class="one-third column space-y-4">

				<p>I'm a Filipino Web Front-end Designer and Developer based on Cebu City, Philippines.</p>

                <p>I can cater projects or freelance jobs depending on the need of your project. I specialize in front-end development using HTML5 and CSS3 with Tailwind CSS and integrating modern JavaScript frameworks like Vite and Vue.js.</p>

			</div>

            <div class="one-third column space-y-4">

				<p>Since 2008 in the web design and development experience in IT industry, I have honed my skills using the latest trends and flows for web interface.</p>
                <p>I am also experienced in back-end development as a sidekick of Senior Developer like PHP CodeIgniter, Laravel, Wordpress, Drupal which I was exposed to with the companies and clients I have worked for.</p>

			</div>

            <div class="one-third column space-y-4">

				<p>My design for websites focuses on simplicity and user-friendly navigation to help web users. </p>

                <p>So if you have something in mind, send me a message or quote through my e-mail at <a class="text-red-700 hover:underline" href="mailto:dam_gases@yahoo.com">dam_gases@yahoo.com</a>.</p>

				<p class="mt-3"><a href="resume-CV8.pdf" target="_blank" rel="noopener noreferrer"><Button variant="default"><DownloadIcon />Download my CV/Resume</Button></a></p>

			</div>

     </section>
</template>