<template>
  <div class='todo-list'>
    <div>
        <input v-model="todo" @keyup.enter="add" type="text">
        <button @click="add" >新增</button>
    </div>
    <ul class="list-group">
        <li v-for="item in items" :key="item">
            <span>{{item}}</span>

            <button @click="remove(item)">
                <span>&times;</span>
            </button>
        </li>
    </ul>
  </div>
</template>

<script steup>
  //todo function
   const toDo = () =>{
   const todo = Vue.ref('');
   const items = Vue.ref(['Vue','is','Awesome']);   
  }
  //新增功能
  const add = () => {
      if (todo.value) {
          items.value.push(todo.value);
          todo.value ='';
      };
  };
  //移除功能
  const remove = item => {
      item.value = items.value.filter( v => v !== item);
  }
  return{
      toDo,
      items,
      add,
      remove
  };

</script>

<style scoped>

</style>