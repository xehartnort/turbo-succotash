<template>
  <v-app>
    
      
    
    <v-toolbar app>
      <v-toolbar-title>Gestor de exámenes</v-toolbar-title>
      <v-spacer />
      <!--<v-switch v-model="subheader" class="ma-2" label="Subheader"></v-switch>
      La idea es habilitar o quitar el modo oscuro
      -->
      <v-toolbar-items>
        <v-dialog v-model="dialog" persistent>
          <template v-slot:activator="{ on }">
            <v-btn icon v-on="on">
              <v-icon>mdi-plus-circle</v-icon>
            </v-btn>
          </template>
          <v-card>
            <v-card-title>
              Subir documentos
            </v-card-title>
            <v-card-text>
              Textooooo, notar que falta añadir un botón para cerrar este diálogo si se añade la propiedad persistent
            </v-card-text>
          </v-card>
        </v-dialog>

        <v-dialog v-model="dialog2" persistent>
          <template v-slot:activator="{ on }">
            <v-btn icon v-on="on">
              <v-icon>mdi-information</v-icon>
            </v-btn>
          </template>
          <v-card>
            <v-card-title>
              Ayuda
            </v-card-title>
            <v-card-text>
              Textooooo, notar que falta añadir un botón para cerrar este diálogo  si se añade la propiedad persistent
            </v-card-text>
          </v-card>
        </v-dialog>
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
