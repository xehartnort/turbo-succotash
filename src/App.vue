<template>
  <v-app>
    <v-toolbar max-height="64px" app>
      <v-toolbar-title>Gestor de exámenes</v-toolbar-title>
      <v-spacer />
      <!--<v-switch v-model="subheader" class="ma-2" label="Subheader"></v-switch>
      La idea es habilitar o quitar el modo oscuro
      -->
      <v-toolbar-items>
        <uploader
          title="Añadir documentos"
          text="Las subidas están limitadas a 3 documentos por usuario y día"
        />
        <about
          title="Sobre nosotros"
          text="Este texto es de prueba, quizás estaría chachi que el sobre nosotros estuviera al final??? y esto fuera una zona donde se describe como se usa la aplicación"
        />
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-card>
        <v-card-title primary-title>Resultados</v-card-title>
        <doc-list :docs="docs" />
      </v-card>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>Made with Vue, Vuex, Vuetify and 💚</span>
    </v-footer>
  </v-app>
</template>

<script>
import DocList from "@/components/DocList.vue";
import Uploader from "@/components/Uploader.vue";
import About from "@/components/About.vue";

export default {
  name: "App",
  components: {
    DocList,
    Uploader,
    About
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
          id: 1,
          description: "rainbows keep falling on my head"
        },
        {
          filename: "examen 2",
          selected: false,
          id: 2,
          description: "rainbows keep falling on my head"
        }
      ];
    }
  }
};
</script>
