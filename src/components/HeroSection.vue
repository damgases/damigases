<script setup lang="ts">

</script>

<template>
    <section id="hero"
        class="flex gap-4 items-end justify-center min-h-[calc(100vh-200px)]">
        <div class="fixed top-0 left-0 w-full z-0">
            <img src="/bg-dami.jpg" alt="Profile Picture" class="w-full h-[100vh] object-cover object-[50%_50%] shadow-lg" />
        </div>
        <div class="relative z-2 flex flex-col items-center space-y-4 px-4">
            <h1 class="text-white text-4xl md:text-5xl font-bold">Hi, I'm <span class="text-primary">Dami Gases</span></h1>
            <p class="text-white text-lg md:text-xl leading-tight">A Web Front-end Designer and Developer</p>

            <!-- <div class="flex space-x-4 mt-4">
                <a href="https://github.com/damigases" target="_blank" rel="noopener noreferrer">
                    <Button variant="ghost" size="icon">
                        <GithubIcon class="w-6 h-6 text-gray-700" />
                    </Button>
                </a>
                <a href="https://linkedin.com/in/damigases" target="_blank" rel="noopener noreferrer">
                    <Button variant="ghost" size="icon">
                        <LinkedinIcon class="w-6 h-6 text-blue-700" />
                    </Button>
                </a>
            </div> -->
        </div>
        
    </section>
</template>