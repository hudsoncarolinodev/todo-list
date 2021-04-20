<template>
  <div class="home">
    <div class="app_content">
      <h2>Adicionar novas tarefa</h2>
      <div class="app_content__formulario">
        <input type="text" placeholder="Adicionar nova tarefa">
        <textarea placeholder="Descrição Tarefa" ></textarea>
        <button>Adicionar</button>

        <h3>Lista de tarefas</h3>
        <ul>
          <li>
            <span>X</span>
            <h1>Nome Tarefa</h1>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
          </li>
        </ul>
      </div>
    </div>
    <div class="app_content">
      <h2>Tarefas concluidas</h2>
      <ul>
        <li>
            <span>X</span>
            <h1>Nome Tarefa</h1>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
          </li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  
}
</script>
