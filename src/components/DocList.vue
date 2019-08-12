<template>
  <v-list>
    <doc v-for="doc in docs" :key="doc.id" :doc="doc"></doc>
  </v-list>
</template>

<script>
import Doc from "@/components/Doc.vue";

export default {
  name: "doc-list",
  componets: {
    Doc
  },
  props: {
    docs: Array
  }
};
</script>