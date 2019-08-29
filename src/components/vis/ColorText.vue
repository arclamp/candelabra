<template>
  <v-card
    outlined
    width="300"
    height="300"
  >
    <v-card-title>
      <span :style="style">Hello World</span>
    </v-card-title>
  </v-card>

</template>

<script>
export default {
  name: 'ColorText',
  props: {
    color: String,
  },
  computed: {
    style () {
      return `color:${this.color}`;
    },
  },
};
</script>
