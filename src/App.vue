<script setup>
  import { reactive } from 'vue';
import TodoForm from './components/TodoForm.vue'
  import TodoList from './components/TodoList.vue'


  
  // console.log(list);
  
</script>
<script>
  export default {
    
  }

  const state = reactive({
    list : []
  })
</script>
<template>
    <div class="main">
          <TodoForm :state="state" />
          <TodoList :state="state" />
    </div>
</template>

<style scoped>

</style>
