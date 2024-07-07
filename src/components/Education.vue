<script setup>
import { useDataStore } from '@/stores/Data'

const dataStore = useDataStore()
</script>
<template>
    <!-- Education -->
    <section class="max-w-screen-lg w-full flex px-4 items-center timeline timeline-snap-icon timeline-vertical">
        <div class="relative w-full h-full flex items-center justify-center mt-28">
            <h2 class="absolute opacity-20 text-7xl font-bold mb-8">Education</h2>
            <h2 class="text-4xl text-slate-50 font-bold mb-8">Education</h2>
        </div>

        <ul class="timeline timeline-snap-icon max-md:timeline-compact timeline-vertical">
            <li v-for="(school, index) in dataStore.educations">
                <hr v-if="index > 0 ? 'hidden' : ''" class="bg-violet-600" >
                <div class="timeline-middle">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="h-5 w-5">
                        <path fill-rule="evenodd"
                            d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z"
                            clip-rule="evenodd" />
                    </svg>
                </div>
                <div :class="index % 2 === 0 ? 'timeline-end' : 'timeline-start md:text-end'">
                    <time class="font-mono italic mx-2">{{ school.granduate }}</time>
                    <div class="timeline-box bg-neutral max-w-lg shadow-2xl">
                        <div class="text-md font-bold">{{ school.school }}</div>
                        <div class="text-sm italic text-slate-300">{{ school.major }}</div>
                        <div v-if="school.gpax !== '' ? 'hidden' : 'my-4'" class="badge badge-outline">{{
                            school.ranges
                        }}
                        </div><br>
                        <div v-if="school.gpax !== '' ? 'hidden' : ''"
                            class="badge bg-base-content text-black mt-4 font-semibold">GPAX: {{ school.gpax }}
                        </div>
                        <div class="my-4">{{ school.about }}</div>
                    </div>
                </div>
                <hr class="bg-violet-600" />
            </li>
        </ul>
    </section>
</template>