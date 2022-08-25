<template>
  <div>
    <label :for="id">{{label}}</label>
    <input type="date" :id="id" v-model="value">
  </div>
</template>

<script>
export default {
  name: "InputDate",
  props: {
    label: {
      type: String,
      required: true,
      validator(value) {
        return typeof (value) === 'string';
      }
    },
    id: String,
    modelValue: Date
  },
  emits: ['update:modelValue'],
  computed: {
    value: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value);
      }
    }
  }
}
</script>

<style scoped>

</style>