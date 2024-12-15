<template>
    <v-container class="fill-height">
        <h1 style="width: 100%; text-align: center;"> Projects </h1>
        <v-carousel hide-delimiter-background>
            <v-carousel-item v-for="item in carouselItems">
                <main-carousel-item 
                    :image_url="item.src"
                    :title="item.title"
                    :year="item.year"
                    :description="item.description"
                    :links="item.links"
                    :tags="item.tags"
                />
            </v-carousel-item>
            <v-carousel-item>
                <multi-carousel-item 
                    :image_urls="jamItem.src"
                    :title="jamItem.title"
                    :year="jamItem.year"
                    :description="jamItem.description"
                    :links="jamItem.links"
                    :tags="jamItem.tags"
                />

            </v-carousel-item>

        </v-carousel>
        <v-divider> </v-divider>
        <AboutMe />
        <v-divider> </v-divider>
        <Contact />
        <v-divider> </v-divider>
        <div style="height: 200px"></div>   
    </v-container>
</template>

<script lang="ts">

import nikochat from '@/assets/carouselgifs/nikochat.gif'
import photochemistry from '@/assets/carouselgifs/photochemistry2.gif'
import vanishingpoint from '@/assets/carouselgifs/vanishingpoint.gif'
import compcon from '@/assets/carouselgifs/compcon.gif'
import pilotdash from '@/assets/carouselgifs/pilotdash.gif'
import phonymicropackers from '@/assets/carouselgifs/phonymacropackers.gif'
import sandsgrowing from '@/assets/carouselgifs/sandsgrowing.gif'
import spirithexagon from '@/assets/carouselgifs/spirithexagon.gif'

import SteamIcon from '@/assets/logos/steam-1.svg'
import GameJoltIcon from '@/assets/logos/gamejolt-svgrepo-com.svg'
import ItchIcon from '@/assets/logos/itchio.svg'
import VideoIcon from '@/assets/logos/youtube-svgrepo-com.svg'
import GitHubIcon from '@/assets/logos/github-142-svgrepo-com.svg'

const carouselItems = [
    { 
        src: photochemistry,
        title: 'Photochemistry',
        year: '2024',
        description: 'My biggest personal project to date. After receiving tons of positive feedback for the jam version, I spent nearly half a year polishing and refining the game into a self-published Steam release, complete with 20+ levels, Steam leaderboards, a rich story-line, and a level editor.',
        links: [
            {text: 'Steam', url: 'https://store.steampowered.com/app/2917850/Photochemistry/', icon: SteamIcon},
            {text: 'Game Jolt (Demo)', url: 'https://gamejolt.com/games/Photochemistry/902784', icon: GameJoltIcon},
            {text: 'itch.io (Jam Version)', url: 'https://tchorne.itch.io/photochemistry', icon: ItchIcon},
            {text: 'Gameplay Video', url: 'https://www.youtube.com/watch?v=fBQo1_YTMmc', icon: VideoIcon}
        ],
        tags: ["Game", "Godot"]
    },
    { 
        src: compcon,
        title: 'COMP/CON ÁINE',
        year: '2024',
        description: 'A fork of the beautifully designed online compedium and character builder for the Lancer TTRPG developed using Vue. I expanded on the site with a 3D map and diagetic tools for my players to decode secret messages they recieve in game.',
        links: [
            {text: 'Live Site', url: 'http://thomashorne.ca:2434/#/map'},
            {text: 'GitHub', url: 'https://github.com/tchorne/compcon-aine', icon: GitHubIcon}
        ],
        tags: ["Website", "Vue", "TypeScript"]
    },    
    {
        src: vanishingpoint,
        title: 'Vanishing Point',
        year: '2024',
        description: 'A puzzle game about objects that stop existing when you look away. Utilizes various shader techniques for the stylized graphics and uses raytracing to implement the main mechanic.',
        links: [
            {text: 'itch.io', url: 'https://itch.io/jam/cu-2024-february-game-jam/rate/2563969', icon: ItchIcon},
            {text: 'Gameplay Video', url: 'https://www.youtube.com/watch?v=qBooQuzO-Io', icon: VideoIcon}
        ],
        tags: ["Game", "Godot"]
    },
    { 
        src: nikochat,
        title: 'NikoChat',
        year: '2023',
        description: 'What good is a portfolio without a ChatGPT wrapper? NikoChat is an expressive LLM-powered chat bot built using Python and Godot. An emotion classifier model allows it to display a number of expressions using custom user images. It utilizes vector storage for long-term retention, can connect to several AI services, and even integrates with Discord and Twitch.',
        links: [
            {text: 'GitHub', url: 'https://github.com/tchorne/NikoChat', icon: GitHubIcon}
        ],
        tags: ["Application", "Godot", "Python"]
    },
]
const jamItem = {
        src: [pilotdash, phonymicropackers, sandsgrowing, spirithexagon],
        title: "Jam Projects",
        year: "Since 2018",
        description: "I’ve been participating in game development competitions for over 6 years now, both solo and in teams. With every project I try to experiment with new genres and techniques to expand my array of skills.",
        links: [{text: 'itch.io', url: 'https://tchorne.itch.io/', icon: ItchIcon},],
        tags: ["Game", "Godot", "Unity"]
}

export default {
    data() {
        return {
            carouselItems: carouselItems,
            jamItem: jamItem
        }
    }
}
</script>