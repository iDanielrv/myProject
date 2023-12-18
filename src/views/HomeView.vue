<script setup>
</script>

<template>
  <div class="container">
    <div class="headerContent">
      <div class="description">
        <h1 class="title">TaskHub: Sua Plataforma de Gerenciamento de Tarefas Colaborativas</h1>
        <p class="text">
          Bem-vindo à TaskHub, a solução ideal para gerenciar projetos e tarefas de forma eficiente. Aumente a colaboração, acompanhando o progresso e alcance seus objetivos com nossa plataforma intuitiva.
        </p>
        <v-btn color="#8685EF">Criar conta agora</v-btn>
      </div>
      <div class="image">
        <img src="/Screenshot.png" alt="">
      </div>
    </div>
  </div>
  <v-icon icon="mdi-antenna"></v-icon>
</template>



<style setup>
.container {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.headerContent {
  display: flex;
  flex-direction: row;
  height: 27.875rem;
  width: 67.5rem;
  background-color: #2B2B2B;
}

.description {
  padding-bottom: 3rem;
  padding-top: 3rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-left: 10%;
  color: white;
  width: 50%;
  
}

.text {
  color: #A3A3A3;
}

.image {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
  background-color: #333333;
  margin-left: 4rem;
}
</style>

<!--  -->