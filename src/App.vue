<template>
  <div class="contents">
    <h1>DnD Demo</h1>
    <TaskList></TaskList>
  </div>
</template>

<script>
import TaskList from './components/task-list.vue';

export default {
  components: { TaskList }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap');

.contents {
  font-family: 'Noto Sans', sans-serif;
}
</style>