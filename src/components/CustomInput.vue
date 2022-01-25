<template>
  <label>
    {{label}}
    <input :type="type" v-model="inputValue" />
  </label>
</template>

<script>
export default {
  name: 'LoginForm',
  computed: {
    inputValue: {
      get () {
        return this.modelValue
      },
      set (value) {
        // console.log(value)
        this.$emit('update:modelValue', value) // can emit an event other components can listen to
        // v-model will listen update event
      }
    }
  },
  props: {
    // props: ['label', 'type', 'modelValue'],
    label: String,
    type: String,
    modelValue: String
  }
}
</script>
