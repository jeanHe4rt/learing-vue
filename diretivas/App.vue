<template>
  <div>
    <h1> Minha lista de Tarefas!</h1>
    <button @click="() => showList = !showList">
      Ver a lista
    </button>
    <br>
    <br>
    <input type="text" v-focus>
    <br>
    <ul v-if="showList">
      <li 
        v-for="(task, index) in tasks"
        :key="`${task}-${index}`"
      >
        {{ task.name }}
      </li>
    </ul>
    <p v-else>Lista escondida</p>
  </div>
</template>

<script>
const focus = {
  inserted: (elemento) => {
    elemento.focus();
  }
}
export default {
  directives:{
    focus  
  },

  data:() => ({
    showList: false,
    tasks: [{
      name: 'Fazer curso',
      isDOne: false
    }]
  })
}
</script>

<style>

</style>