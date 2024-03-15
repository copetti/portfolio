<template>
    <div class="bg-gray-900 py-14">
        <div class="mx-auto max-w-7xl px-6 text-center lg:px-8">
            <div class="mx-auto max-w-2xl">
                <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">My Portfolio</h2>
                <p class="mt-4 text-lg leading-8 text-gray-300">This portfolio was created using Vue.js and Tailwind CSS.</p>
            </div>
            <ul role="list" class="mx-auto mt-20 grid max-w-2xl">
                <li>
                    <img class="mx-auto h-56 w-56 rounded-full" :src="profile.image" alt="" />
                    <h3 class="mt-6 text-base font-semibold leading-7 tracking-tight text-gray-900">{{ profile.name }}</h3>
                    <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">{{ profile.role }}</h2>
                    <div class="mx-auto mt-2 space-x-2">
                        <img v-for="(tag, index) in tags" :key="index"
                             target="_blank"
                             class="inline-flex items-center"
                             height="30"
                             width="40"
                             :src="`images/${tag}`"
                        />
                    </div>
                    <ul role="list" class="mt-6 flex justify-center gap-x-6">
                        <li>
                            <a :href="profile.github" target="_blank" class="text-gray-400 hover:text-gray-500">
                                <span class="sr-only">GitHub</span>
                                <svg class="h-10 w-10" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                                <path d="M8 0c4.42 0 8 3.58 8 8a8.013 8.013 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38 0-.27.01-1.13.01-2.2 0-.75-.25-1.23-.54-1.48 1.78-.2 3.65-.88 3.65-3.95 0-.88-.31-1.59-.82-2.15.08-.2.36-1.02-.08-2.12 0 0-.67-.22-2.2.82-.64-.18-1.32-.27-2-.27-.68 0-1.36.09-2 .27-1.53-1.03-2.2-.82-2.2-.82-.44 1.1-.16 1.92-.08 2.12-.51.56-.82 1.28-.82 2.15 0 3.06 1.86 3.75 3.64 3.95-.23.2-.44.55-.51 1.07-.46.21-1.61.55-2.33-.66-.15-.24-.6-.83-1.23-.82-.67.01-.27.38.01.53.34.19.73.9.82 1.13.16.45.68 1.31 2.69.94 0 .67.01 1.3.01 1.49 0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8Z"></path>
                                </svg>
                            </a>
                        </li>
                        <li>
                            <a :href="profile.linkedinUrl" target="_blank" class="text-gray-400 hover:text-gray-500">
                                <span class="sr-only">LinkedIn</span>
                                <svg class="h-8 w-8" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                                    <path fill-rule="evenodd" d="M16.338 16.338H13.67V12.16c0-.995-.017-2.277-1.387-2.277-1.39 0-1.601 1.086-1.601 2.207v4.248H8.014v-8.59h2.559v1.174h.037c.356-.675 1.227-1.387 2.526-1.387 2.703 0 3.203 1.778 3.203 4.092v4.711zM5.005 6.575a1.548 1.548 0 11-.003-3.096 1.548 1.548 0 01.003 3.096zm-1.337 9.763H6.34v-8.59H3.667v8.59zM17.668 1H2.328C1.595 1 1 1.581 1 2.298v15.403C1 18.418 1.595 19 2.328 19h15.34c.734 0 1.332-.582 1.332-1.299V2.298C19 1.581 18.402 1 17.668 1z" clip-rule="evenodd" />
                                </svg>
                            </a>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    name: 'Profile',

    data(){
        return {
            profile : {
                name: 'André Copetti',
                role: 'Software Engineer',
                image:'images/profile.png',
                github: 'https://github.com/copetti',
                linkedinUrl: 'https://www.linkedin.com/in/andré-copetti/',
            },
            tags: ['laravel.svg', 'vuejs.svg', 'livewire.svg', 'php.svg', 'javascript.png', 'mysql.png', 'pest.png', 'docker.svg', 'forge.png']
        }
    }
}

</script>