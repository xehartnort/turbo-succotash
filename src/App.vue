<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title>Gestor de exámenes</v-toolbar-title>
      <v-spacer />
      <v-toolbar-items>
        <v-btn icon>
          <v-icon>mdi-home</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-plus-circle</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-information</v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-flex xs12 sm8 offset-sm2 md6 offset-md3>
        <v-card>
          <v-card-title primary-title>
            <h1>Doc list</h1>
          </v-card-title>
          <doc-list :docs="docs"></doc-list>
        </v-card>
      </v-flex>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>Made with Vue, Vuex, Vuetify and 💚</span>
    </v-footer>
  </v-app>
</template>

<script>
import DocList from "@/components/DocList.vue";

export default {
  name: "App",
  components: {
    DocList
  },
  data() {
    return {
      fixed: false
    };
  },
  computed: {
    docs() {
      return [
        {
          filename: "examen 1",
          selected: true,
          id: 1
        },
        {
          filename: "examen 2",
          selected: false,
          id: 2
        }
      ];
    }
  }
};
</script>
