<template>
  <v-card color="transparent" flat>
    <v-list color="transparent" nav>
      <v-list-item v-for="(item,index) in items" :key="index" :to="item.to" v-text="item.name" />
    </v-list>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      items: [
        { name: 'ForEach', to: { name: 'native-js-foreach' } },
        { name: 'map', to: { name: 'native-js-map' } },
        { name: 'Every', to: { name: 'native-js-every' } }
      ]
    }
  }
}
</script>

<style>

</style>
