<template>
  <div class="select_author ms-auto mt-2">
    <label class="me-2 text-white" for="author">Seleziona un artista:</label>
  <select
      name="author"
      id="author"
      :value="typeAuthor"
      @input="$emit('input', $event.target.value)"
      @change="$emit('selectAuthor')"
    >
      <option value="" selected>All</option>
      <option>Bon Jovi</option>
      <option>Queen</option>
      <option>Sting</option>
      <option>Iron Maiden</option>
      <option>Eric Clapton</option>
      <option>Deep Purple</option>
      <option>Dave Weckl</option>
      <option>Michael Jacjson</option>


    </select>
    
  </div>
</template>

<script>
export default {
    name:'SelectAuthor',
    props:{
        typeAuthor: String
    }
}
</script>

<style lang="scss" scoped>
select {
  width: 200px;
}
</style>

