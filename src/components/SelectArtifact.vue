<template>
  <div>
    <v-select
      data-width="100%"
      v-model="selected"
      :value="selected"
      label="name"
      :options="artifacts"
      @input="setSelected"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import vSelect from 'vue-select';
import 'bootstrap-select';
import { en } from '../assets/js/en.artifacts';
import 'vue-select/dist/vue-select.css';

export default Vue.extend({
  components: { vSelect },
  data() {
    return {
      selected: null,
      artifacts: en,
    };
  },
  methods: {
    setSelected(value: { _id: string; name: string }): void {
      this.$emit('input', value.name);
    },
  },
});
</script>
