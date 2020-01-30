<template>
  <div class="sample_frame">
    <slot name="sample_title"></slot>
    <slot name="sample_cont"></slot>
  </div>
</template>

<script>
export default {
  name: 'SampleFrame'
}
</script>

<style scoped>
  .sample_frame {
    border: dashed 2px #41B883;
    max-width: 70%;
    margin: 50px auto 100px;
    padding: 10px 20px;
  }
</style>
