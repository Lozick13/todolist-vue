<template>
  <div class="add-task">
    <add-task-form v-if="isFormVisible" @addTask="addTask" />

    <clear-button class="add-task__button" @click="toggleFormVisibility">
      <img src="@/assets/plus.png" alt="Добавление" />
    </clear-button>
  </div>
</template>

<script>
import AddTaskForm from '@/components/AddTask/AddTaskForm';
export default {
  data() {
    return {
      isFormVisible: false,
    };
  },

  components: {
    AddTaskForm,
  },
  methods: {
    addTask(task) {
      this.isFormVisible = false;
      this.$emit('addTask', task);
    },
    toggleFormVisibility() {
      this.isFormVisible = !this.isFormVisible;
    },
  },
};
</script>

<style scoped>
.add-task {
  position: fixed;
  bottom: 50px;
  right: 50px;
  display: flex;
  gap: 20px;
}
img {
  width: 100px;
}
button.add-task__button {
  opacity: 1;
}
button.add-task__button:hover {
  opacity: 0.7;
}
@media (max-width: 500px) {
  .add-task {
    bottom: 15px;
    right: 15px;
    flex-direction: column;
    align-items: flex-end;
  }
  img {
    width: 50px;
  }
}
</style>
