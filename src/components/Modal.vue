<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <!-- content inside the tags acts as fallback -->
      <slot>default content</slot>
      <div class="actions">
        <slot name="links"></slot>
        <slot name="img"></slot>
      </div>
    </div>
  </div>
</template>

<script>

export default ({
  props: [
    'theme'
  ],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
})
</script>


<style>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background-color: rgba(0, 0, 0, .5);
    width: 100%;
    height: 100%;
  }
  .modal h1 {
    color: #03cfb4;
    border: none;
    padding: 0;
  }
  .modal p {
    color: #333;
    border: none;
    padding: 0;
  }
  .modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
  }
  .modal .actions a {
    color: #333;
    border: 1px solid #eee;
    border-radius: 4px;
    padding: 8px;
    text-decoration: none;
    margin: 10px;
  }
  .modal.sale {
    background-color: crimson;
  }
  .modal.sale,
  .modal.sale h1,
  .modal.sale .actions,
  .modal.sale .actions a{
    color: white;
  }
</style>