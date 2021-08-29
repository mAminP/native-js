<template>
  <v-app>
    <v-main>
      <v-container class=" fill-height d-flex justify-center align-center">
        <v-row align="center" justify="center">
          <v-col ref="el" cols="auto">
            <nuxt />
          </v-col>
          <v-col cols="12" class="d-flex flex-row align-center justify-center">
            <v-btn rounded large @click="snapShot">
              snap Shot
            </v-btn>
            <v-btn
              class="mx-3"
              exact
              rounded
              large
              icon
              :to="{name: 'native-js'}"
            >
              <v-icon>mdi-arrow-right</v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  methods: {
    async snapShot () {
      const el = this.$refs.el
      const options = { type: 'dataURL' }
      const shot = await this.$html2canvas(el, options)
      window.open(
        shot,
        '_blank'
      )
    }
  }
}
</script>

<style>
.editor {
  /* background: #2d2d2d; */
  /* color: #ccc; */

  font-family: Fira code, Fira Mono, Consolas, Menlo, Courier, monospace;
  font-size: 14px;
  line-height: 1.5;
}

.prism-editor__textarea:focus {
  outline: none;
}
</style>
