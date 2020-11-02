<template>
  <div class="todo">
      <Todolist />
  </div>
</template>

<script>
// @ is an alias to /src
import Todolist from '../components/todolist';
export default {
  name: "todo",
  components: {
   Todolist,
   
  }
};
</script>