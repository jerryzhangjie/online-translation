<template>
  <div id="translationOutput">
    <h3 id="showtext" v-text="showtext"></h3>
  </div>
</template>

<script>

export default {
  name: 'translationOutput',
  props: ['showtext']
}
</script>

<style>
  #showtext {
    color: green;
  }
</style>
