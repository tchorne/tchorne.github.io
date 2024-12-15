<template>
  <div class="header">
    <v-container>
      <v-row>
        <v-col>
          <h1> Thomas Horne </h1>
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

export default {
  name: 'MyHeader',
  data() {
    return {
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

</style>
