<template>
  <v-container fluid>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="visComponents"
          outlined
          label="Visualization"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      visComponents: null,
    };
  },

  mounted () {
    this.visComponents = [
      'Foobar',
    ];
  },
};
</script>
