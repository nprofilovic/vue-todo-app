<template>
  <div class="todo-item" :class="{'is-completed':todo.completed}">
    <p>
      <input type="checkbox" :checked="todo.completed" @change="markComplete">
      {{ todo.title }}
      <button class="del" @click="$emit('del-todo', todo.id)">x</button>
    </p>
  </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props: ["todo"],

        methods: {
            markComplete () {
                this.todo.completed = !this.todo.completed
            }
        }
    }
</script>

<style scoped>
    .todo-item {
        background: #f4f4ff;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }
    .is-completed {
        text-decoration: line-through;
    }
    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>