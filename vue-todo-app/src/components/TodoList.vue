<template>
    <div class="todoContainer"> 
        <a class="btn btn-danger" @click="removeTodo(id)">
            <span class="icon">
                <i class="fa fa-trash-o" aria-hidden="true"></i>
            </span>
            <span>Remove</span>
        </a>
        <span class="todoText">{{text}}</span>
    </div> 
</template>

<script>

export default {
  name: 'todoList',
  props: ['id', 'text'],
  methods: {
      removeTodo(id) {
          this.$parent.removeTodo(id);
      }
  }
}
</script>

<style>
@import '../assets/TodoForm.css';
</style>
