<template>
    <div class="container mx-auto px-5 py-5 h-screen">
        <div class="flex flex-col">
            <div v-if="showDate" class="grid lg:grid-cols-3 md:grid-cols-2 xl:grid-cols-4">
                <div class="p-4 m-5 w-full flex items-center">
                    <h2>{{ getCurrentTime() }}</h2>
                </div>
            </div>
            <div class="grid lg:grid-cols-3 md:grid-cols-2 xl:grid-cols-4">
                <a :href="link.url" target="_blank" class="p-4 m-5 w-full flex items-center rounded-lg hover:bg-slate-400" v-for="link in services"
                    :key="link.title">

                        {{ link.title }}<br />
                        {{ link.description }}

                </a>
            </div>
        </div>
    </div>
</template>

<script>
import settings from './assets/config/settings.json';

export default {
    created() {
        document.title = this.title;
    },
    data() {
        return settings;
        /*return {
            title: "Homebase",
            links: [
                {
                    title: "Plex",
                    description: "Personal Media Server",
                    url: "https://plex.mattseemon.in"
                },
                {
                    title: "Sonarr",
                    description: "Personal TV show manager",
                    url: "https://sonarr.mattseemon.in"
                },
                {
                    title: "Radarr",
                    description: "Personal movie manager",
                    url: "https://radarr.mattseemon.in"
                },
                {
                    title: "Overseerr",
                    description: "Media request management systems",
                    url: "https://overseerr.mattseemon.in"
                },
                {
                    title: "Tautulli",
                    description: "Plex media server monitoring",
                    url: "https://tautulli.mattseemon.in"
                }
            ],
            showDate: true
        }*/
    },
    methods: {
        getCurrentTime() {
            return new Date().toString()
        }
    }
}
</script>