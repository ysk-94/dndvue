<template>
  <h3>Default</h3>
  <draggable v-model="newTasks" @start="drag=true" @end="onDragEnd" item-key="id" group="tasks">
    <template #item="{element}">
      <div :id="element.id" class="task">{{element.id}} | {{element.title}} | {{element.date}} | {{element.author}}</div>
    </template>
  </draggable>
  <h3>Progressing</h3>
  <draggable v-model="progressing" @start="drag=true" @end="onDragEnd" item-key="id" group="tasks">
    <template #item="{element}">
      <div :id="element.id" class="task">{{element.id}} | {{element.title}} | {{element.date}} | {{element.author}}</div>
    </template>
  </draggable>
</template>

<script>
import draggable from 'vuedraggable';
import Task from './task.vue';

export default {
  components: { Task, draggable },
  data() {
    return {
      newTasks: [
        {
          id: 1,
          title: 'Buy some tickets.',
          date: '2021/2/22',
          author: 'dad'
        },
        {
          id: 2,
          title: 'Fix the sofa.',
          date: '2021/2/25',
          author: 'dad'
        },
        {
          id: 3,
          title: 'Boil the pasta.',
          date: '2021/2/28',
          author: 'dad'
        }
      ],
      progressing: [
        {
          id: 4,
          title: 'Buy some coffee beans.',
          date: '2021/2/22',
          author: 'dad'
        },
        {
          id: 5,
          title: 'Fix the humidifier.',
          date: '2021/2/25',
          author: 'dad'
        },
        {
          id: 6,
          title: 'Dig a well.',
          date: '2021/2/28',
          author: 'dad'
        }
      ]
    }
  },
  methods: {
    // dndevent
    onDragEnd(args) {
      console.log(args); // newIndexで移動先が取れそう
      console.log(args.newIndex);
      console.log(this.newTasks);
      console.log(this.progressing);
    }
  },
}
</script>

<style>
.task {
  cursor: pointer;
}
</style>