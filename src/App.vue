<script setup lang="ts">
// import HelloWorld from './components/HelloWorld.vue';
import LatestProjects from '@/components/LatestProjects.vue';
import LegacyProjects from '@/components/LegacyProjects.vue';
import AdProjects from '@/components/AdProjects.vue';
import AdMiniProjects from '@/components/AdMiniProjects.vue';
import About from '@/components/About.vue';
import HeroSection from '@/components/HeroSection.vue';
import { Button } from "@/components/ui/button";
import { ChevronDownIcon, UserIcon, PencilRulerIcon } from 'lucide-vue-next';
import { Menubar, MenubarContent, MenubarItem, MenubarMenu, MenubarSeparator, MenubarTrigger } from "@/components/ui/menubar";

</script>

<template>
  
  <Menubar class="fixed top-0 right-0 left-0 z-10 !bg-black/50 !border-0 !h-18 !rounded-none">
    <div class="flex items-center justify-center gap-2 md:gap-4 h-18 w-full">
      <a href="#about">
          <Button type="button" variant="outline" size="lg" class="text-base"><UserIcon/> About Me</Button>
      </a>
      <MenubarMenu>
        <MenubarTrigger as-child><Button type="button" variant="default" size="lg" class="text-base"><PencilRulerIcon/> My Projects <ChevronDownIcon /></Button></MenubarTrigger>
        <MenubarContent>
          <MenubarItem as="a" href="#latest_projects" rel="noopener noreferrer" class="text-white bg-primary">Latest Projects</MenubarItem>
          <MenubarSeparator />
          
          <MenubarItem as="a" href="#legacy_projects" rel="noopener noreferrer">Legacy Projects</MenubarItem>
          <MenubarItem as="a" href="#ad_projects" rel="noopener noreferrer">Ad Projects</MenubarItem>
          <MenubarItem as="a" href="#ad_mini_projects" rel="noopener noreferrer">Ad Mini Projects</MenubarItem>
        </MenubarContent>
      </MenubarMenu>
    </div>
  </Menubar>

  <HeroSection />
  <br id="latest_projects"><br></br>

  <div id="projects" class="relative z-3 bg-background p-4 md:px-6 md:py-10 rounded-xl">
    <LatestProjects />
    <br id="legacy_projects"><br></br>
    <LegacyProjects />
    <br id="ad_projects"><br></br>
    <AdProjects />
    <br id="ad_mini_projects"><br></br>
    <AdMiniProjects />
    <br id="about"><br><br>

    <About />
    <br><br></br>
  </div>


    <footer class="relative z-4 clearfix pt-8">

      <div class="flex flex-wrap justify-center items-center">

        <div class="twelve columns">

          <h6 class="text-center text-base text-gray-300 my-8">
            <p>Copyright © 2012 damigases.com. All Rights Reserved</p>
          </h6>

        </div>

      </div>

    </footer>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
