<template>
  <header class="header">
    <h1 class="title">Tarefas</h1>
  </header>
</template>

<script>
export default {
  name: 'MainHeader',
};
</script>

<style scoped>
.header {
  background-color: #f5f5f5;
  color: #333;
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.title {
  font-size: 24px;
  font-weight: bold;
  margin: 0;
}
</style>
