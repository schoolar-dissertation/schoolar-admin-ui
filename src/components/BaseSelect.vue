<template>
  <div class="form-group">
    <label v-if="label">{{ label }}</label>
    <select class="custom-select" v-model="model" :value="value">
      <option v-if="hasNone" :value="null">None</option>
      <option v-for="item in options" :value="item.value" :key="item.id">{{
        item.label
      }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'base-select',
  props: {
    label: {
      type: String,
      required: true
    },
    value: {
      type: [String, Number],
      default: null
    },
    v: {
      type: Object,
      required: true
    },
    options: {
      type: Array,
      required: true
    },
    hasNone: {
      type: Boolean,
      default: true
    }
  },
  computed: {
    model: {
      get() {
        return this.value;
      },
      set(value) {
        this.v.$touch();
        this.$emit('input', value);
      }
    }
  }
};
</script>
