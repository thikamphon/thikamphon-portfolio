<script setup>
import { useDataStore } from '@/stores/Data'
import CandyAdventure from '@/assets/candy-adventure.webp'
import { ref } from 'vue'
const dataStore = useDataStore()
const isModalOpen = ref(false);
const modalVideo = ref(null);

const openModal = () => {
    isModalOpen.value = true;
    nextTick(() => {
        modalVideo.value.play();
    });
};

const closeModal = () => {
    isModalOpen.value = false;
    if (modalVideo.value) {
        modalVideo.value.pause();
        modalVideo.value.currentTime = 0;
    }
};

const handleEsc = (e) => {
    if (e.key === 'Escape') {
        closeModal();
    }
};
</script>
<template>
    <section class="py-14 mx-4 max-w-screen-lg md:mx-14">
        <div class="relative w-full h-full flex items-center justify-center mt-28">
            <h2 class="absolute opacity-20 text-7xl font-bold mb-8">Projects</h2>
            <h2 class="text-4xl text-slate-50 font-bold mb-14">Projects</h2>
        </div>
        <div
            class="w-fit justify-items-center grid grid-cols-1 gap-4 sm:grid-cols-2 md:grid-cols-2 md:gap-4 md:mx-auto lg:grid-cols-3">
            <button @click="openModal" class="card-hover card min-w-72 max-w-96 bg-neutral shadow-lg p-2"
                onclick="my_modal_2.showModal()">
                <figure>
                    <img class="object-cover object-top aspect-video rounded-xl" :src="CandyAdventure" alt="overview of project: Trailer:game by unity">
                </figure>
                <div class="card-body p-4">
                    <h2 class="card-title text-start">
                        Trailer: Candy Adventre-Game
                    </h2>
                    <p class="line-clamp-3 text-start">
                        The trailer all of the process used Unity and free assets in
                        Unity asset. In the project, I was
                        used for learning.
                    </p>
                    <div class="card-actions justify-end">
                        <div class="badge badge-outline">Unity</div>
                        <div class="badge badge-accent">University</div>
                    </div>
                </div>
            </button>
            <dialog v-if="isModalOpen" @click="closeModal" id="my_modal_2" class="modal">
                <div class="modal-box">
                    <video ref="modalVideo" controls autoplay class="aspect-video rounded-xl">
                        <source src="../assets/videos/Game-2D-Candy.mp4" type="video/mp4">
                        Your browser does not support the video tag.
                    </video>
                    <div class="my-4">
                        <h1 class="font-semibold text-xl">Trailer: Candy Adventre-Game</h1>
                        <p class="line-clamp-3 text-start">
                            The trailer all of the process used Unity and free assets in
                            Unity asset. In the project, I was
                            used for learning.
                        </p>
                    </div>
                    <div class="flex justify-end mt-8"><button class="btn btn-sm">close</button>
                    </div>

                </div>
                <form method="dialog" class="modal-backdrop" @click="closeModal" @keyDown="handleEsc">
                    <button>close</button>
                </form>
            </dialog>
            <div v-for="(project, index) in dataStore.projects" :key="index"
                class="card-hover card min-w-72 max-w-96 bg-neutral shadow-lg p-2">
                <a :href="project.link" target="_blank">
                    <figure>
                        <img class="object-cover object-top h-52 w-full rounded-xl" :src="project.imageUrl"
                            :alt="`overview of project: ` + project.title" />
                    </figure>
                    <div class="card-body p-4">
                        <h2 class="card-title">
                            {{ project.title }}
                        </h2>
                        <p class="line-clamp-3">
                            {{ project.about }}
                        </p>
                        <div class="card-actions justify-end">
                            <div v-for="(tag, index) in project.tags" :key="index"
                                :class="tag === 'University' ? 'badge badge-accent' : 'badge badge-outline'">{{
                                    tag }}
                            </div>
                        </div>
                    </div>
                </a>
            </div>

        </div>
    </section>
</template>

<style scoped>
.card-hover {
    @apply hover:scale-95 hover:duration-300
}
</style>