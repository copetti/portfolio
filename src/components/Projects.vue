<template>
    <div class="bg-gray-900 py-5">
        <div class="mx-auto max-w-7xl px-6 text-center lg:px-8">
            <div class="mx-auto max-w-2xl">
                <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">My Projects</h2>
                <p class="mt-4 text-lg leading-8 text-gray-400">
                    My study projects are still in development phase, and I'm using Laravel Forge for deployment.
                </p>
            </div>
            <ul role="list" class="mx-auto mt-20 grid max-w-2xl grid-cols-1 gap-6 sm:grid-cols-2 lg:mx-0 lg:max-w-none lg:grid-cols-3 lg:gap-8">
                <li v-for="project in projects" :key="project.name" class="rounded-2xl bg-gray-800 px-8 py-10">
                    <img class="mx-auto h-48 w-48 rounded-full md:h-56 md:w-56" :src="project.imageUrl" alt="" />
                    <h3 class="mt-6 text-base font-semibold leading-7 tracking-tight text-white">{{ project.name }}</h3>
                    <p class="text-sm leading-6 text-gray-400">{{ project.tecnologies }}</p>

                    <div class="mx-auto mt-2 space-x-2">
                        <span
                            v-for="(tag, index) in tags" :key="index"
                            class="inline-flex items-center rounded-md bg-pink-400/10 px-2 py-1 text-xs font-medium text-pink-400 ring-1 ring-inset ring-pink-400/20 uppercase"
                        >
                            {{ tag }}
                        </span>

                        <img v-for="(tag, index) in project.tags" :key="index"
                           target="_blank"
                           class="inline-flex items-center"
                           height="30"
                           width="40"
                           :src="`images/${tag}`"
                        />
                    </div>
                    <p class="text-sm leading-6 text-gray-400 mt-2">{{ project.description }}</p>
                    <span class="isolate inline-flex rounded-md shadow-sm mt-4 space-x-2 mt-2">
                        <a
                            v-if="project.githubapp"
                            target="_blank"
                            :href="project.githubapp"
                            class="rounded-md bg-white/10 px-2.5 py-1.5 text-sm font-semibold text-white shadow-sm hover:bg-white/20"
                        >
                           Github
                        </a>
                        <a
                            v-if="project.live_preview"
                            target="_blank"
                            :href="project.live_preview"
                            class="rounded-md bg-white/10 px-2.5 py-1.5 text-sm font-semibold text-white shadow-sm hover:bg-white/20"
                        >
                           Preview
                        </a>
                    </span>
                </li>
            </ul>
        </div>
    </div>
</template>


<script>

export default {
    name: 'Profile',

    data() {
        return {
            projects: [
                {
                    name: 'CRM Livewire',
                    description: 'This course focuses on developing a CRM system. It covers project management setup on Notion, task planning, and implementation using technologies like Livewire v3, TailwindCSS, MaryUi, Laravel (backend), and Pest.',
                    tecnologies: 'Laravel + Livewire + TailwindCSS + Pest',
                    imageUrl:'images/crm.png',
                    live_preview: 'https://crm-livewire-v3.copetti.dev/',
                    githubapp: 'https://github.com/copetti/crm-livewire-v3',
                    githubapi: '#',
                    tags: ['laravel.svg', 'livewire.svg', 'tailwindcss.svg', 'pest.png']
                },
                {
                    name: 'SaaS',
                    description: 'Within this project, I\'m implementing the entire authentication flow, subscription plans, integration with Stripe for payments. This project is utilizing Laravel on the backend through an API and Vue.js on the front end.',
                    tecnologies: 'Laravel + Vue JS + Vuetify + Pinia',
                    imageUrl:'images/image-app.png',
                    live_preview: 'https://appoint-me-app.copetti.dev/',
                    githubapp: 'https://github.com/copetti/appoint-me-app',
                    githubapi: 'https://github.com/copetti/appoint-me-api',
                    tags: ['laravel.svg', 'vuejs.svg', 'vuetify.png', 'pinia.png']
                },
                {
                    name: 'Pest Driven Laravel',
                    description: 'Learning to write applications that are fully tested through TDD',
                    tecnologies: 'Laravel + Pest',
                    imageUrl:'images/pest-image.png',
                    live_preview: '',
                    githubapp: 'https://github.com/copetti/pest-driven-laravel',
                    githubapi: '',
                    tags: ['laravel.svg', 'pest.png']
                }
            ],

        }
    }
}



</script>
