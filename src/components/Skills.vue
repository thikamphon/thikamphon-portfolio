<script setup>
import IconGithub from '@/assets/icons/icon_git.webp';
import IconHtml from '@/assets/icons/icon_html.webp';
import IconCss from '@/assets/icons/icon_css.webp';
import IconJs from '@/assets/icons/icon_js.webp';
import IconVue from '@/assets/icons/icon_vue.webp';
import IconReact from '@/assets/icons/icon_react.webp';
import IconTailwind from '@/assets/icons/icon_tailwind.webp';
import IconUnity from '@/assets/icons/icon_unity.webp';
import IconCsharp from '@/assets/icons/icon_c.webp';

const skills = [
    { name: 'html', icon: IconHtml, },
    { name: 'css', icon: IconCss, },
    { name: 'Javascript', icon: IconJs, },
    { name: 'Vue', icon: IconVue, },
    { name: 'React', icon: IconReact, },
    { name: 'Tailwind', icon: IconTailwind, },
    { name: 'C Sharp', icon: IconCsharp, },
    { name: 'Unity', icon: IconUnity, },
    { name: 'Github', icon: IconGithub, },
]
</script>

<template>
    <!-- Skills -->
    <section class="w-full flex flex-col items-center mt-28">
        <div class="relative w-full h-full flex items-center justify-center">
            <h2 class="absolute opacity-20 text-7xl font-bold mb-8">Skills</h2>
            <h2 class="text-4xl text-slate-50 font-bold mb-8">Skills</h2>
        </div>
        <div class="card min-w-sm mx-8 max-w-lg bg-neutral text-neutral-content shadow-2xl">
            <div class="card-body items-center text-center">
                <p class="italic">"Over the months, I have cultivated and refined a diverse set of skills through
                    dedicated
                    study and practical experience. Below are the key abilities I have developed."</p>
                <div class="card-actions justify-center items-center">
                    <div v-for="skill in skills"
                        class="flex items-center py-1 rounded-lg gap-4 w-fit h-11 sm:border sm:px-4">
                        <!-- <component class="fill-slate-200 w-6 h-full" :is="skill.icon"></component> -->
                        <img class="fill-slate-200 w-6 h-fit" :src="skill.icon" :alt="skill.icon">
                        <span class="sr-only block w-fit sm:not-sr-only">{{ skill.name }}</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>