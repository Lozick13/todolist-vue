<template>
  <section class="tasks">
    <task-item
      @taskDelete="$emit('taskDelete', task)"
      v-for="task in tasks"
      :key="task.id"
      :task="task"
    />
  </section>
</template>

<script>
import TaskItem from '@/components/Task/TaskItem';

export default {
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  components: {
    TaskItem,
  },
};
</script>

<style scoped>
.tasks {
  display: flex;
  flex-direction: column;
  gap: 30px;
}
</style>
