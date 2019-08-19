<template>
  <v-app>
    <v-app-bar :flat="!compact" app>
      <v-toolbar-title
        v-if="compact"
        class="mr-12 align-center d-none d-sm-flex"
      >
        <span class="title">Custom Name</span>
        <!-- hide on small screens, replace name with icon -->
      </v-toolbar-title>
      <v-row align="center">
        <v-text-field
          v-if="compact"
          v-model="userinput"
          placeholder="Buscar..."
          clearable
          hide-details
          prepend-icon="mdi-magnify"
        />
      </v-row>
      <v-spacer />
      <v-toolbar-items>
        <uploader title="Añadir documentos" />
        <about
          title="Sobre nosotros"
          text="Este texto es de prueba, quizás estaría chachi que el sobre nosotros estuviera al final??? y esto fuera una zona donde se describe como se usa la aplicación"
        />
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
      <v-card>
        <v-card-text>
          Supongo que aquí irá un gran logo centrado y debajo el nombre
        </v-card-text>
        <v-text-field
          v-model="userinput"
          v-if="!compact"
          placeholder="Buscar..."
          clearable
          prepend-icon="mdi-magnify"
        />
        <doc-list v-if="search" :docs="docs" />
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
      fixed: false,
      compact: true, // determina en que modo se cuentra el sistema
      search: false, // tan pronto como se realize una búsqueda se mostrarán los resultados
      loading: false // representa un icono de carga mientras se obtienen los resultados
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
