<template>
  <select v-model="selectedOption" @change="selectOption"> 
    <option value=""> Filtra per genere</option>
    <option v-for="option in options" :key="option.value || option " :value="option.value || option"> 
      {{ option.label || option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "BaseSelect",
  props: {
    options: Array, 
  },
  data() {
    return {
      selectedOption: '',
    }
  },
  methods: {
    selectOption() {
      this.$emit("change-option", this.selectedOption )
    }
  }
};
</script>

<style lang="scss" scoped>
</style>