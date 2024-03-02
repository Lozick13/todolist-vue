<template>
  <div class="to-do-list">
    <header-to-do-list />
    <main class="main">
      <task-list @taskDelete="taskDelete" :tasks="tasks" />
    </main>
    <add-task-block @addTask="addTask" />
  </div>
</template>

<script>
import HeaderToDoList from '@/components/HeaderToDoList';
import TaskList from '@/components/Task/TaskList';
import AddTaskBlock from '@/components/AddTask/AddTaskBlock';

export default {
  data() {
    return {
      tasks: [
        { id: 1, title: 'Task', mark: 'Mark', date: '01-01-1999' },
        { id: 2, title: 'Task', mark: 'Mark', date: '01-01-1999' },
        { id: 3, title: 'Task', mark: 'Mark', date: '01-01-1999' },
      ],
    };
  },
  methods: {
    taskDelete(task) {
      this.tasks = this.tasks.filter(el => el !== task);
    },
    addTask(task) {
      this.tasks.push(task);
    },
  },
  components: {
    HeaderToDoList,
    TaskList,
    AddTaskBlock,
  },
};
</script>

<style>
* {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.to-do-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.main {
  padding: 50px 0;
}
</style>
