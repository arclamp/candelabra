<template>
  <v-container fluid>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
          :items="visComponentNames"
          label="Visualization"
          @change="showVis"
          outlined
        />
      </v-col>
    </v-row>

    <v-row>
      <v-col class="d-flex" cols="12" sm="6">
        <color-text v-if="mode == 'ColorText'"
          color="red"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import * as vis from './vis';

export default {
  components: {
    ColorText: vis.ColorText,
  },

  data () {
    return {
      visComponents: vis,
      mode: null,
    };
  },

  computed: {
    visComponentNames () {
      return Object.keys(this.visComponents);
    },
  },

  methods: {
    showVis (vis) {
      this.mode = vis;
    }
  },
};
</script>
