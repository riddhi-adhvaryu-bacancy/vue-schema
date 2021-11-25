<template>
  <v-app>
    <v-main>
      <SchemaForm/>
    </v-main>
  </v-app>
</template>

<script>
import SchemaForm from './components/SchemaForm';

export default {
  name: 'App',

  components: {
    SchemaForm,
  },

  data: () => ({
    //
  }),
};
</script>
