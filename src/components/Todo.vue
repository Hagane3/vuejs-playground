<script>
export default {
  data() {
    return {
      inputValue: "",
      todos: [
        {
          id: 1,
          title: "Learn Vue",
          completed: false,
        },
        {
          id: 2,
          title: "Learn React",
          completed: false,
        },
        {
          id: 3,
          title: "Learn Angular",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      if (this.inputValue === "") return;
      this.todos.push({
        id: this.todos.length + 1,
        title: this.inputValue,
        completed: false,
      });
    },
    inputHandler(e) {
      this.inputValue = e.target.value;
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo);
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>TODO APP</h1>
    <div class="add-input">
      <input @input="inputHandler" />
      <button class="add-btn" @click="addTodo">Add</button>
    </div>
    <div class="todos" v-for="todo in todos" :key="todo.id">
      <div>
        <input type="checkbox" v-model="todo.completed" />
        <span :class="{ done: todo.completed }">{{ todo.title }}</span>
        <button @click="removeTodo(todo)">x</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  background-color: lightgoldenrodyellow;
  padding: 5em;
  text-align: center;
}

.add-input {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1em;
}

.add-btn {
  padding: 0.1em 1em;
}

.todos {
  margin-top: 1em;
  border: 1px solid black;
  min-height: 5em;
  display: flex;
  justify-content: center;
  align-items: center;
}

.todos > div {
  display: flex;
  gap: 1em;
}

.done {
  text-decoration: line-through;
}

.todos > div > button {
  padding: 0.2em;
}
</style>
