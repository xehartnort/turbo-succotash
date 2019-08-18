<template>
  <v-dialog v-model="dialog" persistent max-width="600px">
    <template v-slot:activator="{ on }">
      <v-btn icon v-on="on">
        <v-icon>mdi-plus-circle</v-icon>
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        {{ title }}
      </v-card-title>
      <v-card-text>
        <v-form ref="form" v-model="valid">
          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail de la UGR"
            required
          />
          <v-file-input
            :rules="docRules"
            accept="image/*,application/pdf"
            label="Documentos"
            display-size
            counter
            chips
            multiple
            required
          ></v-file-input>
        </v-form>
      </v-card-text>
      <v-card-actions>
        <v-spacer />
        <v-btn color="blue darken-1" text @click="dialog = false">Cerrar</v-btn>
        <v-btn color="blue darken-1" text @click="validate">
          GUAT!?
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "uploader",
  props: {
    title: String
  },
  data: () => ({
    dialog: false,
    emailRules: [
      v => !!v || "Campo obligatorio",
      v =>
        /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@correo\.ugr\.es$/.test(v) ||
        "El e-mail debe ser válido"
    ],
    docRules: [
      v => v.length > 0 || "Campo obligatorio",
      v => v.length <= 3 || "Máximo 3 documentos"
    ]
  }),
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        return true;
      }
    }
  }
};
</script>
