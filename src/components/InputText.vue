<template>
<div>
  <label :for="id">{{label}}</label>
  <input type="text" :id="id" v-model="value">
</div>
</template>

<script>
export default {
  name: "InputText",
  props: {
    label: String,
    id: String,
    modelValue: String
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
input{
  font-family: Arial, sans-serif;
  font-size: 20pt;
}
div {
  margin: 10px;
  padding: 5px;
}

label {
  margin: 3px;
  color: red;
}
</style>