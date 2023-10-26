<template>
  <div class='todo-list'>
    <div>
        <input v-model="todo" @keyup.enter="add" type="text">
       <!-- v-model 雙向 當add時會把text加入-->
        <button @click="add" >新增</button>
      <!--點擊會觸發add增加項目-->
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
   const items = Vue.ref(['Dog','Cat','Apple']);   //初始任務
  
  
  //新增功能
  const add = () => {
      if (todo.value) {
          items.value.push(todo.value); 
          todo.value ='';
      };
  };
  //移除功能
  const remove = item => {
    item.value = items.value.filter(v => v !== item);
  }
  //當ｖ和item相等,會被過濾掉

  return{
      todo,
      items,
      add,
      remove
  };
};
</script>

<style scoped>

</style>