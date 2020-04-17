<template>
  <div class="title flex-centered" :class="{checked: todo.checked}">
    <div class="title-icon">
      <i class="icon" :class="todo.checked ? 'icon-check' : 'icon-time'"></i>
    </div>
    <div class="title-content">
      <div class="title-subtitle">{{todo.description}}</div>
    </div>
    <div class="title-action">
      <button @click="$emit('toggle', todo)" class="btn btn-link">
        <span v-if="todo.checked">Desmarcar</span>
        <span v-else>Concluído</span>
      </button>
      <button class="btn btn-link">
        <span @click="$emit('remove', todo)" class="text-erro">Remover</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: { type: Object, required: true }
  }
};
</script>

<style>
.checked {
  text-decoration: line-through;
  color: lightgray;
}
</style>