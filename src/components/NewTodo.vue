<template>
<div>
    <input type="text" v-model="doTo" >
    <button @click="addNewTodo()">Add</button>
</div>
</template>

<script>
export default {
    name: "NewTodo",
    data(){
        return{
            doTo:"",
        }
    },
    methods:{
        addNewTodo(){
            this.$emit('sendNewToDo',this.doTo);
            this.doTo="";
        }
    }
}
</script>

<style scoped>

</style>