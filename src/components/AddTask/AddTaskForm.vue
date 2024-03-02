<template>
  <form @submit.prevent>
    <base-input v-model="task.title" placeholder="Название задания" />
    <base-input v-model="task.mark" class="mark" placeholder="Метка" />
    <base-input v-model="task.date" class="date" type="date" />
    <clear-button @click="addTask" class="add">
      <img src="@/assets/enter.png" alt="Добавить" />
    </clear-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      task: {
        title: '',
        mark: '',
        date: '',
      },
    };
  },
  methods: {
    addTask() {
      if (!this.task.title && !this.task.mark && !this.task.date) {
        return;
      }

      this.task.id = Date.now();
      this.$emit('addTask', this.task);

      this.title = '';
      this.mark = '';
      this.date = '';
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  align-items: center;
  padding: 0 20px;
  gap: 10px;
  background-color: #e5ffe6;
  height: 100px;
  border-radius: 16px;
  border: 2px solid #000;
}
img {
  width: 40px;
}
.mark {
  width: 120px;
}
.add {
  opacity: 1;
}
.add:hover {
  opacity: 0.7;
}
@media (max-width: 500px) {
  form {
    padding: 20px;
    height: 100%;
    flex-direction: column;
    align-items: center;
  }
  .mark {
    width: auto;
  }
  .date {
    width: 100%;
    background: white;
  }
}
</style>
