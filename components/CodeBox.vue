<template>
  <v-card elevation="6" rounded="xl" min-width="300">
    <client-only placeholder="Loading...">
      <prism-editor v-model="code" class="editor pa-3" :highlight="highlighter" line-numbers />
    </client-only>
  </v-card>
</template>

<script>
// import Prism Editor
import { PrismEditor } from 'vue-prism-editor'
import 'vue-prism-editor/dist/prismeditor.min.css' // import the styles somewhere

// import highlighting library (you can use any library you want just return html string)
import { highlight, languages } from 'prismjs/components/prism-core'
import 'prismjs/components/prism-clike'
import 'prismjs/components/prism-javascript'
import 'prismjs/themes/prism-tomorrow.css' // import syntax highlighting styles

export default {
  components: {
    PrismEditor
  },
  props: {
    // eslint-disable-next-line vue/require-default-prop
    value: {
      type: String
    }
  },
  computed: {
    code: {
      get () {
        return this.value
      },
      set (value) {
        this.$emit('input', value)
      }
    }
  },
  methods: {

    highlighter (code) {
      return highlight(code, languages.js) // returns html
    }
  }
}
</script>
