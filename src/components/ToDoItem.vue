<template>
  <div class="item">
    {{value}}
    <button @click="deleteTodo" class="delete-btn">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: {
    value: String
  },
  emits: ['delete'],
  methods: {
    deleteTodo() {
      this.$emit('delete')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .item {
    color: #2e3440;
    background: #88c0d0;
    padding: 10px;
    margin: 10px;
    width: 400px;
    border-radius: 5px;
    word-break: break-all;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .item .delete-btn {
    color: #2e3440;
    background: #d8dee9;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    flex-shrink: 0;
    margin-left: 5px;
    padding: 5px;
  };
</style>
