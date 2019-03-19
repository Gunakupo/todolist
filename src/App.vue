<template>
  <div>
    <h1>Todo List App</h1>
    <input-button v-model="inputText" @submitit="handleSubmit"></input-button>
    <p v-if="todolists.length===0">Nothing left in the list. Add a new todo in the input above.</p>
    <ul v-else>
      <list v-for="(todo,index) in todolists" :key="index" :content="todo" :index="index" @delete="deleteIt"></list>
    </ul>
  </div>
</template>

<script>
import list from './components/list';
import inputButton from './components/inputButton';
export default {
  name: 'app',
  components: {
    'list':list,
    'input-button':inputButton
  },
  data:function(){
    return {
      inputText:"",
      todolists:[]
    }
  },
  methods:{
    handleSubmit:function(value){
      this.todolists.push(value);
    },
    deleteIt:function(index){
      this.todolists.splice(index,1);
    }
  }
}
</script>

<style scoped>
  div{max-width: 400px; margin: 0 auto;line-height: 1.4;text-align: center;color: #666;}
  p{text-align: left;}
</style>

