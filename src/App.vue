<template>
  <MainHeader v-show="showHeader" />
  
  <div v-show="showName" class="section">
    <div>Nome: {{ firstName }}</div>
    <div>Sobrenome: {{ lastName }}</div>
  </div>

  <div v-show="showLevel" class="section">
    <div v-if="accessLevel === 'admin'" class="level">Nível Admin</div>
    <div v-else-if="accessLevel === 'marketing'" class="level">Nível Marketing</div>
    <div v-else class="level">Usuário Comum</div>
  </div>

  <div v-for="(todo, index) in todos" :key="todo.id" class="todo">
    {{ index + 1 }} - {{ todo.title }}
  </div>
</template>

<script>
import MainHeader from "./components/MainHeader.vue";

export default {
  name: "App",
  components: {
    MainHeader,
  },
  data() {
    return {
      showHeader: true,
      firstName: "Jon",
      lastName: "Snow",
      showName: true,
      showLevel: true,
      accessLevel: "admin", // Exemplo de nível de acesso
      todos: [
        { userId: 1, id: 1, title: "delectus aut autem", completed: false },
        { userId: 1, id: 2, title: "quis ut nam facilis et officia qui", completed: false },
        { userId: 1, id: 3, title: "fugiat veniam minus", completed: false },
        { userId: 1, id: 4, title: "et porro tempora", completed: true },
        { userId: 1, id: 5, title: "laboriosam mollitia et enim quasi adipisci quia provident illum", completed: false },
        { userId: 1, id: 6, title: "qui ullam ratione quibusdam voluptatem quia omnis", completed: false },
      ],
    };
  },
};
</script>

<style scoped>
.section {
  margin-bottom: 20px;
}

.level {
  font-weight: bold;
  color: #0b33a1; /* Green color */
}

.todo {
  background-color: #f2f2f2; /* Light gray background */
  padding: 10px;
  margin-bottom: 5px;
  border-left: 6px solid #0b33a1; /* Green border left */
}
</style>
