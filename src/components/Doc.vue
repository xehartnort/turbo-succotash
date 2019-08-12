<template>
  <v-list-tile>
    <v-list-tile-content>
      <v-list-tile-title :class="{selected: doc.selected}">{{ doc.filename }}</v-list-tile-title>
    </v-list-tile-content>
  </v-list-tile>
</template>

<script>
export default {
  name: "doc",
  props: {
    doc: Object
  }
};
</script>

<style lang="scss" scoped>
.selected {
  text-decoration: line-through;
}
</style>