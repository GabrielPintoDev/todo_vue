<script setup>
const props = defineProps(['tarefas']);
</script>

<template>

    <p v-if="props.tarefas.length === 0" class="mt-4">Nenhuma tarefa encontrada</p>
    <ul class="list-group mt-4" v-else>
        <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>