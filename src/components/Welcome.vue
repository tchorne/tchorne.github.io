<template>
    <v-container class="fill-height">
        <h1> Hello world</h1>
        <v-carousel>
            <v-carousel-item v-for="item in carouselItems">
                <h1> {{ item.src }}</h1>
            </v-carousel-item>
        </v-carousel>
    </v-container>
</template>

<script lang="ts">
export default {
    data() {
        return {
            carouselItems: [
                { src: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' },
                { src: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' },
                { src: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' },
                { src: 'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' },
            ]
        }
    }
}
</script>