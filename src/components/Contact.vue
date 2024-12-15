<template>
    <div style="width: 100%">
        <h1 style="width: 100%; text-align: center;"> Get in Touch </h1>
        <v-container class="fill-width">
            <v-row>
                <v-col cols="6">
                    <div style="width: 100%; height: 100%; display: flex; align-items: center; justify-content: center;">

                        <v-btn variant="outlined" href="./resume.pdf" color="primary" size="x-large">View my resume</v-btn>
                    </div>
                </v-col>
                <v-col cols="6">
                    <div style="width: 100%; height: 100%; display: flex; align-items: center; justify-content: center;">
                        <v-btn variant="outlined" href="mailto:tchorne2@gmail.com" color="primary" size="x-large">tchorne2@gmail.com</v-btn>
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </div>

</template>

<script lang="ts">

const ABOUTME = `I’m a student at Carleton University in Ottawa, Canada. When I’m not pursuing my Bachelors in Computer Science, I’m working on games.

I’ve been developing games since I was 10 years old. My expertise lies in gameplay, systems, and graphics programming as that’s where my personal projects overlap with my education, but I dabble in all aspects of game development from level design to playtesting analysis.

Besides game development and programming, I enjoy running, cooking, and tabletop RPGs. I have several years of experience as a Dungeon Master, and I always bring my ability to improve the player experience to the table.
`
export default {
    name: "AboutMe",
    data() {
        return {
            ABOUTME
        }
    },
    directives: {
    }
}
</script>

<style scoped>
.about-me {
    font-size: 1.2em;
    white-space: pre-wrap;
}

.me-img {
    width: 100%;
    object-fit: contain;
    border-radius: 10px;
}

</style>
