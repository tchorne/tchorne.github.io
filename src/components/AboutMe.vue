<template>
    <div>
        <h1 style="width: 100%; text-align: center;"> About Me </h1>
        <v-container>
            <v-row >
                <v-col cols="6">
                    <p class="about-me">
                        {{  ABOUTME }}
                    </p>
                </v-col>
                <v-col cols="6">
                    <v-img class="me-img" src="@/assets/me.jpg" transition="scroll-x-transition" />
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
