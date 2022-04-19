<template>
  <div>
    <TodoInputText
      v-model="newTodoText"
      @keydown.enter="addTodo"
      @add="addTodo"
    />
    <ul class="no-bullet" v-if="todos.length">
      <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @remove="removeTodo"
      />
    </ul>
    <p class="no-item" v-else>
      You have done <i>everything</i>. Add a new todo in the input above.
    </p>
  </div>
</template>

<script>
import TodoInputText from "./TodoInputText.vue";
import TodoListItem from "./TodoListItem.vue";

let nextTodoId = 1;

export default {
  components: {
    TodoInputText,
    TodoListItem,
  },
  data() {
    return {
      newTodoText: "",
      todos: [
        {
          id: nextTodoId++,
          text: "Learn Vue",
        },
        {
          id: nextTodoId++,
          text: "Discover single-file components",
        },
        {
          id: nextTodoId++,
          text: "Arrive at the end of the day alive",
        },
        {
          id: nextTodoId++,
          text: "Be happy",
        },
        {
          id: nextTodoId++,
          text: "Water the plants",
        },
      ],
    };
  },
  methods: {
    addTodo() {
      const trimmedText = this.newTodoText.trim();
      if (trimmedText) {
        this.todos.push({
          id: nextTodoId++,
          text: trimmedText,
        });
      }
      this.newTodoText = "";
    },
    removeTodo(idToRemove) {
      this.todos = this.todos.filter((todo) => todo.id !== idToRemove);
    },
  },
};
</script>
<style scoped>
.no-item {
  padding: 30px 10px;
  color: cornsilk;
  text-align: center;
}
.no-bullet {
  border-radius: 5px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  list-style-type: none;
  margin-top: 25px;
  padding: 0;
}
</style>