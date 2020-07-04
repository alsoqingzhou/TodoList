<template>
  <li @click="handleClick">{{content}}</li>
</template>

<script>
export default {
  props:['content','position'],
  methods:{
    handleClick (){
      this.$emit('delete', this.position)
    }
  }
}
</script>

<style scoped>

</style>
