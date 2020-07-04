<template>
  <div>
    <input v-model="inputValue">
    <button @click="handleSubmit">Submit</button>
    <ul>
      <todo-item 
      v-for="(item, index) of list"
      v-bind:key="index"
      :content="item"
      :position="index"
      @delete="handleDelete"
      >
      </todo-item>
    </ul>
  </div>
</template>

<script>

import TodoItem from './components/TodoItem'

export default {
  components: {
    "todo-item": TodoItem
  },
  data () {
    return{
      inputValue:"",
      list: [],
    }
  },
  methods: {
    handleSubmit (){
      this.list.push(this.inputValue);
      this.inputValue = '';
    },

    handleDelete (position){
      this.list.splice(position, 1)
    }
  }
}
</script>

<style>

</style>
