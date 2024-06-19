<template>
  <MainHeader v-show="showHeader" />

  <div v-show="showName" class="section name-section">
    <div>Nome: {{ firstName }}</div>
    <div>Sobrenome: {{ lastName }}</div>
  </div>

  <div class="section image-section">
    <img :src="userImgSrc" :alt="userImgAlt" />
  </div>

  <div v-show="showLevel" class="section level-section">
    <div v-if="accessLevel === 'admin'" class="level admin-level">Nível Admin</div>
    <div v-else-if="accessLevel === 'marketing'" class="level marketing-level">Nível Marketing</div>
    <div v-else class="level user-level">Usuário Comum</div>
  </div>

  <div v-for="(todo, index) in todos" :key="todo.id" class="todo-item">
    <div v-if="todo.img" class="todo-img">
      <img :src="todo.img" :alt="todo.alt" />
    </div>
    <div class="todo-text">
      {{ index + 1 }} - {{ todo.title }}
      <i v-if="todo.completed" class="fas fa-check-circle completed-icon"></i>
    </div>
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
      accessLevel: "admin",
      userImgSrc: "https://placehold.co/300x200?text=Hello+World",
      userImgAlt: "Jon Snow",
      todos: [
        {
          userId: 1,
          id: 1,
          title: "delectus aut autem",
          completed: false,
          img: "https://placehold.co/50x40?text=Hello+World",
          alt: this.id,
        },
        {
          userId: 1,
          id: 2,
          title: "quis ut nam facilis et officia qui",
          completed: false,
          img: "https://placehold.co/50x40?text=Hello+World",
          alt: this.id,
        },
        {
          userId: 1,
          id: 3,
          title: "fugiat veniam minus",
          completed: false,
          img: "https://placehold.co/50x40?text=Hello+World",
          alt: this.id,
        },
        {
          userId: 1,
          id: 4,
          title: "et porro tempora",
          completed: true,
          img: "https://placehold.co/50x40?text=Hello+World",
          alt: this.id,
        },
        {
          userId: 1,
          id: 5,
          title:
            "laboriosam mollitia et enim quasi adipisci quia provident illum",
          completed: false,
          img: "https://placehold.co/50x40?text=Hello+World",
          alt: this.id,
        },
        {
          userId: 1,
          id: 6,
          title: "qui ullam ratione quibusdam voluptatem quia omnis",
          completed: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.section {
  margin-bottom: 20px;
  padding: 15px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.name-section {
  background-color: #f9f9f9;
}

.image-section img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.level-section {
  text-align: left;
}

.level {
  font-weight: bold;
  padding: 10px;
  border-radius: 5px;
  color: #fff;
}

.admin-level {
  background-color: #007bff; /* Blue background */
}

.marketing-level {
  background-color: #17a2b8; /* Teal background */
}

.user-level {
  background-color: #28a745; /* Green background */
}

.todo-item {
  display: flex;
  align-items: center;
  background-color: #f9f9f9;
  padding: 10px;
  margin-bottom: 10px;
  border-left: 6px solid #007bff; /* Blue border left */
  border-radius: 5px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.todo-img img {
  width: 50px;
  height: 40px;
  margin-right: 10px;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.todo-text {
  font-size: 16px;
  color: #333;
  display: flex;
  align-items: center;
}

.completed-icon {
  color: #28a745; /* Green color for completed tasks */
  margin-left: 10px;
}
</style>
