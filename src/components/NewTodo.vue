<template>
<div>
    <div class="col">
        <div class="row">
            <input class="new-todo m-3 p-3" type="text" v-model="doTo" @keypress.enter="addNewTodo" >
        </div>
        <div class="row">
            <button class="m-3 p-3 mx-5 px-5" @click="addNewTodo()">Add</button>
        </div>
    </div>
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
.new-todo{
    background: #f3ebeb;
    border: 3px solid #c57272;
    border-radius: 5px;
    box-shadow: 1px 0px 3px;
    color: black;
}
button{
    width: fit-content;
    background-color: #c57272;
    border: none;
    border-radius: 5px;
    box-shadow: 1px 2px 3px;
}
.row{
    display: flex;
    flex-direction: row;
    justify-content: center;
    text-align: center;
    align-items: center;
}
</style>