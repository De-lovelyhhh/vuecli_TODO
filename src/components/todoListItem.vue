<template>
  <li >
    <span :class="todo.flag?'':'isFinish'">
      {{ todo.text }}
    </span>
    <button @click="$emit('remove', todo.id)">
      删除
    </button>
    <button @click="$emit('finish',todo.flag,todo.id)">
      完成
    </button>
  </li>
</template>

<script>
export default {
  name: 'todoListItem',
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.isFinish{
  text-decoration: line-through;
}
</style>
