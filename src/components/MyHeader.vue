<template>
  <div class="header">
    <v-container>
      <v-row>
        <v-col>
          <h1> {{nameText}} <div class='blinker' v-if="blinkerVisible"></div></h1>
        </v-col>
        <v-col class="d-flex justify-end" style="gap: 15px">
          <v-btn variant="outlined" href="./resume.pdf" color="primary" >Resume</v-btn>
          <v-btn variant="outlined" href="mailto:tchorne2@gmail.com" color="primary" >Contact</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">

const NAME = 'Thomas Horne'

export default {
  name: 'MyHeader',
  data() {
    return {
      nameText: NAME,
      blinkerVisible: true
    }
  },
  mounted() {
    this.nameText = ''

    setTimeout(() => {

      this.typeName()

    }, 300)

    

  },
  methods: {
    typeName() {
      this.nameText = ''

      let i = 0

      const interval = setInterval(() => {
        if (i < NAME.length) {
          this.nameText = NAME.slice(0, i + 1)
          i++
        } else {
          clearInterval(interval)
          this.blinkerVisible = false
        }
      }, 150)
    }
  }
}


</script>

<style scoped>

.header {
  height: 60px;
  padding-left: 4vw;
  padding-right: 5vw;
  padding-top: 15px;
}

.blinker {
  display: inline-block;
  width: 3px;
  height: 26px;
  background-color: #fff;
  animation: blinkTextCursor 500ms steps(44) infinite;
}

@keyframes blinkTextCursor{
  from{background-color: rgba(255,255,255,.75);}
  to{background-color: transparent;}
}
</style>
