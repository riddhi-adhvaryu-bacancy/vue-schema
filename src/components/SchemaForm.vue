<template>
  <v-container>
    <h1>Create Form using json-schema</h1>
    <v-jsonschema-form
      v-if="
        schemaData &&
          Object.keys(schemaData).length > 0
      "
      :schema="schemaData"
      :model="modelData"
      :options="schemaOptions"
    />
    <v-btn color="light-blue" @click="saveJson">Save</v-btn
    >
  </v-container>
</template>

<script>

  import Vue from 'vue'
  import Vuetify from 'vuetify'
  import 'vuetify/dist/vuetify.min.css'
  import Draggable from 'vuedraggable'
  import Swatches from 'vue-swatches'
  import 'vue-swatches/dist/vue-swatches.min.css'
  import VJsonschemaForm from '@koumoul/vuetify-jsonschema-form'
  import '@koumoul/vuetify-jsonschema-form/dist/main.css'
  import { Sketch } from 'vue-color'

  Vue.use(Vuetify)

  Vue.component('swatches', Swatches)
  Vue.component('draggable', Draggable)
  Vue.component('color-picker', Sketch)

  export default {
    name: 'SchemaForm',
    components: {
      VJsonschemaForm,
    },
    data: () => ({
      schemaData: require("./schema"),
      modelData: {},
      schemaOptions: {
        "accordionMode": "normal"
      }
    }),
    methods: {
      saveJson() {
        console.log("modelData",this.modelData)
      }
    }
  }
</script>
