<template>
    <v-container class="fill-height fill-width" style="width: 100%;" fluid>
        <v-row class="fill-height">
            <v-col cols="7" class="d-flex flex-wrap" style="margin-left: 50px">
                <div class="image-container" ref="tiltElement" style="width: 45%; height: 45%; margin: auto;" v-for="image_url in image_urls">
                    <div class="blur-background">
                        <img :src="image_url" />
                    </div>
                    <div class="main-image">
                        <v-img :src="image_url" style="width: 100%; height: 100%; object-fit: contain; object-position: center; ">
                            <template v-slot:placeholder>
                            <div class="d-flex align-center justify-center fill-height">
                                <v-progress-circular
                                color="grey-lighten-4"
                                indeterminate
                                ></v-progress-circular>
                            </div>
                            </template>
                        </v-img>
                    </div>
                </div>
                
            </v-col>
            <v-col class="d-flex flex-column" style="padding-bottom: 100px;">
                <v-row>
                    <h1>{{title}} <span class="release-year"> ({{ year }})</span></h1>
                    <p class="description">{{ description }}</p>
                </v-row>
                <v-row align-content="end">
                    <v-btn v-for="link in links" :href="link.url" class="ma-1" variant="outlined" color="primary">
                        <img :src="link.icon" v-if="link.icon" style="width: 20px; height: 20px; margin-right: 5px;" />
                        {{ link.text }}</v-btn>
                </v-row>
            </v-col>
        </v-row>
        
    </v-container>
</template>

<script lang="ts">

import VanillaTilt from 'vanilla-tilt';

export default {
    name: 'MultiItemCarousel',
    data() {
        return {
        }
    },
    props: {
        image_urls: Array<string>,
        title: String,
        description: String,
        year: String,
        links: Array<{text: string, url: string, icon?: string}>,
        tags: Array<String>,
    },
    mounted() {
        nextTick(() => {
            this.initTilt();
        });
    },
    methods: {
        initTilt() {
            VanillaTilt.init(<HTMLElement>this.$refs.tiltElement, {
                max: 2,
                speed: 400,
                glare: true,
                reverse: true,
                'max-glare': 0.1,
                scale: 1.02
            });
        }
    }
    
}
</script>

<style>
.release-year {
    color: #9c9c9c;
    font-size: 1.2rem;
}

.tilt-container {
    transform-style: preserve-3d;
    transform: perspective(1000px); 
}

.image-container {
  position: relative;
  width: 100%;
  height: 100%;
}

.blur-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  filter: blur(12px) brightness(0.7);
  transform: scale(1.02); /* Prevents blur edges from showing */
  z-index: 1;
  object-fit: contain;
    object-position: center;
}

.blur-background img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}

.main-image {
    position: absolute;
    width: 100%;
    height: 100%;
    
    border-radius: 15px;
    z-index: 2;
}

.js-tilt-glare {
    z-index: 3 !important;
}
</style>