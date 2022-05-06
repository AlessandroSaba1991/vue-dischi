<template>
<div class="select_genere ms-auto">
    <label class="me-2 text-white" for="genere">Seleziona un genere:</label>
  <select
      name="genere"
      id="genere"
      :value="typeGenere"
      @input="$emit('input', $event.target.value)"
      @change="$emit('selectGenere')"
    >
      <option>All</option>
      <option>Rock</option>
      <option>Jazz</option>
      <option>Pop</option>
      <option>Metal</option>
    </select>
    
  </div>
</template>

<script>
export default {
  name: "SelectComponent",
  props: {
    typeGenere: String,
  },
};
</script>

<style lang="scss" scoped>
select {
  width: 200px;
}
</style>