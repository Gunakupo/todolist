<template>
    <div>
    <input v-bind:value="inputText" type="text" 
    @input="inputText=$event.target.value" placeholder="todo">
    <button v-on:click="handleSubmit">提交</button>
    </div>
</template>

<script>
export default {
    name:'inputButton',
    data:function(){
        return{
            inputText:''
        }
    },
    methods:{
        handleSubmit(){
            if(this.inputText!==""){
            this.$emit('submitit',this.inputText);
            this.inputText="";}
        }
    }
}
</script>

<style scoped>
  input{width: 80%; padding: 8px 10px ; border: 1px solid #ccc;}
  button{background-color: #fff; width:50px;height: 32px;margin-left:5px ;outline: none;}
</style>


