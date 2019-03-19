<template>
  <li>
    {{content}}
    <button v-on:click="handleDelete">X</button>
  </li>
</template>

<script>
export default {
  name: 'list',
  props: ['content','index'],
  methods:{
    handleDelete:function(){
      this.$emit('delete',this.index);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  li{text-align: left; }
  button{background-color: #fff;outline: none;margin-left:5px ;}
</style>
