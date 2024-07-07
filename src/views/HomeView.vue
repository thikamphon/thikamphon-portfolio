<script setup>
import Skills from '@/components/Skills.vue'
import AboutMe from '@/components/AboutMe.vue'
import Education from '@/components/Education.vue'
import Project from '@/components/Project.vue'
import Footer from '@/components/Footer.vue'
</script>

<template>
  <div class="p-4">
    <div class="w-full h-full bg-base-100 max-w-screen-lg mx-auto border border-none rounded-3xl">
      <div class="navbar rounded-t-3xl bg-base-200">
        <div class="w-full mx-auto flex justify-between">
          <span class="flex font-bold text-xl ml-2 gap-0 py- text-slate-100">
            Thikamphon
            <div class="w-fit font-extrabold text-amber-400">
              .
            </div>
            <span class="w-fit">RB</span>
          </span>
          <a target="_blank"href="https://github.com/thikamphon" class="btn bg-violet-600 text-white w-fit">github profile</a>
        </div>
      </div>
      <AboutMe />
      <div class="w-full flex flex-col gap-y-8 items-center">
        <Skills />
        <Project />
        <Education />
      </div>
      <Footer />
    </div>
  </div>

</template>

<style>
.leading-0 {
  line-height: 0.25rem
}

.z-1 {
  z-index: 1;
}

.hover {
  @apply hover:opacity-60 duration-300
}
</style>