<script setup>
    const props = defineProps(['tarefas'])
</script>

<template>
    <ul class="list-group mt-4" v-if="tarefas.length>0">
        <li class="list-group-item" v-for="tarefa in tarefas">
            <input @change="evento=>tarefa.finalizada=evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.título" type="checkbox">
            <label :class="{done: tarefa.finalizada}" class="ms-3" :for="tarefa.título">
                {{ tarefa.título }}
            </label>
        </li>
    </ul>
    <p v-else class="mt-4 ms-1">
        Não há tarefas pendentes.
    </p>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>