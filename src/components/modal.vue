<template>
  <div class="backdrop" @click.self="handleShowModal">
    <div class="modal" :class="{sale: theme === 'sale'}">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    handleShowModal() {
      this.$emit('closeModal')
    }
  }
}
</script>


<style>
  .modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
  }

  .backdrop{
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
  }

  h1{
    color: red;
  }

  .sale{
    color: green;
  }
</style>