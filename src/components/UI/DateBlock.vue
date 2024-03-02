<template>
  <div class="task__date">
    <img src="@/assets/calendar.svg" alt="Дата" />
    <span>{{ date }}</span>
  </div>
</template>

<script>
export default {
  props: {
    date: {
      type: String,
      required: true,
    },
  },
  name: 'date-block',
};
</script>

<style scoped>
.task__date {
  display: flex;
  align-items: center;
  gap: 5px;
}
.task__date img {
  width: 25px;
}
.task__date span {
  font-size: 15px;
  position: relative;
  top: 1px;
}
</style>
