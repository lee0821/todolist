<template>
  <div>
    <div>
      <input v-model="inputValue"/>
      <button @click="handleClick">提交</button>
    </div>
    <ul>
      <todo-item v-for="(item, index) of list" :key="index" :content="item" :index="index" @delete="itemDelete"></todo-item>  
    </ul>
  </div>  
</template>

<script>
import TodoItem from "./components/TodoItem"

export default {
  components:{
    "todo-item" : TodoItem,
  },
  data: function() {
    return({
      inputValue: '',
      list: [],
      }
    )
  },
  methods: {
    handleClick: function() {
      this.list.push(this.inputValue);
      this.inputValue = '';
    },
    itemDelete: function(index){
      this.list.splice(index, 1);
    }
  }
}
</script>

<style>

</style>
