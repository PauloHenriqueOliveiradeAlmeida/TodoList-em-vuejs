<template>
  <div class="todo">
    <md-field md-clearable class="md-field">
      <label>A Fazer</label>
      <md-input v-model="texto"></md-input>
    </md-field>

    <div>
      <md-button v-on:click="addTodo(texto)" class="md-fab md-primary">
        <md-icon>+</md-icon>
      </md-button>
    </div>
    <div>
      <md-list>
        <md-list-item v-for="todo in todos" v-bind:key="todo.id">
          <span class="md-list-item-text">{{ todo.texto }}</span>
        </md-list-item>
      </md-list>
    </div>
    <md-button
      class="md-raised md-accent"
      v-on:click="clearTodo()"
      v-if="todos.length != 0"
      >Limpar Lista</md-button
    >
  </div>
</template>

<script>
export default {
  name: "todo",
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    addTodo(texto) {
      this.todos.push({
        id: this.todos.length + 1,
        texto: texto,
      });
    },
    clearTodo() {
      this.todos = [];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
.md-field {
  width: 40vw;
}
input {
  transition: all.3s linear;
  animation: select 60s linear infinite;
}
@keyframes select {
  50% {
    border-color: solid 1px blue;
  }
  100% {
    border-color: solid 1px red;
  }
}
</style>
