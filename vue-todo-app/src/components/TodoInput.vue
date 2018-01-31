<template>
    <div class="todoFormContainer">
        <form>
            <input type="text" :value="iText" @input="fetchInput" placeholder="Enter Todo Item" />
            <a class="btn btn-success" @click="saveData">
                <span class="icon">
                    <i class="fa fa-plus" aria-hidden="true"></i>
                </span>
                <span>Add</span>
            </a>
        </form>
    </div>
</template>

<script>

export default {
  name: 'todoInput',
  props: ['iText', 'addTodo'],
  data() {
      return {
        input:''
    }
  },
  methods: {
        fetchInput(event) {
            this.setInput(event.target.value);
        },
        saveData() {
            if(this.input.length > 0)
            {   
                this.$parent.addTodo(this.input);
                this.setInput("");
            }
        },
        setInput(val) {
            this.input = val;
            this.$emit("textChanged", this.input);
       },
    }
  }
</script>

<style>
@import '../assets/TodoForm.css';
</style>
