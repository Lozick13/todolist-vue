<template>
  <div>
    <clear-button @click="$emit('taskDone', task)">
      <img src="@/assets/checked.png" alt="Готово" />
    </clear-button>
    <clear-button @click="$emit('taskDelete', task)">
      <img src="@/assets/bin.png" alt="Удалить" />
    </clear-button>
  </div>
</template>

<script>
export default {
  props: {
    task: {
      type: Object,
      required: true,
    },
  }
};
</script>

<style scoped>
img {
  width: 40px;
}
</style>
