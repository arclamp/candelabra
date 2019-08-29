<template>
  <v-container fluid>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="2">
        <v-select
          :items="visComponentNames"
          label="Visualization"
          @change="showVis"
          outlined
        />
      </v-col>
    </v-row>

    <v-row>
      <v-col class="d-flex" cols="12" sm="3">
        <color-text v-if="mode == 'ColorText'"
          :color="color"
          :message="message"
        />
      </v-col>

      <v-col class="d-flex" cols="12" sm="3">
        <div v-if="mode == 'ColorText'">
          <v-color-picker
            v-model="color"
            hide-inputs
          />

          <v-text-field
            v-model="message"
            outlined
          />

        </div>
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
      color: '',
      message: 'Hello World',
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
