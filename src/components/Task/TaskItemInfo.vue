<template>
  <h2
    class="title"
    :style="{ 'text-decoration': isTitleDone ? 'line-through 5px' : 'none' }"
  >
    {{ task.title }}
  </h2>
  <div class="subinfo">
    <span class="mark"> {{ task.mark }}</span>
    <date-block :date="task.date" />
  </div>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      required: true,
    },
    isTitleDone: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style scoped>
.title {
  font-size: 25px;
}
.subinfo {
  display: flex;
  gap: 30px;
  align-items: center;
}
.mark {
  font-size: 16px;
  padding: 5px 10px;
  color: white;
  border-radius: 5px;
  background: #000;
}
@media (max-width: 500px) {
  .subinfo{
    gap: 10px;
  }
}
</style>
