<template>
  <v-list-item>
    <v-list-item-content>
      <v-list-item-title :class="{ selected: doc.selected }">{{
        doc.filename
      }}</v-list-item-title>
      <v-list-item-subtitle>{{ doc.description }}</v-list-item-subtitle>
    </v-list-item-content>
  </v-list-item>
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
