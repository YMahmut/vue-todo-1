<template>
    <div>
        <ul>
            <li v-for="(todo,index) in todos" :key="todo.id">
                {{todo.name}}
                <button @click="DeleteTodo(index)">Delete</button>
            </li>
        </ul>
        <NewTodo @sendNewToDo="todos.push({id:todos.length+1, name:$event})"/>
    </div>

</template>

<script>
import NewTodo from "./NewTodo"
export default {
    components:{
        NewTodo
    },
    name: "ToDo",
    data(){
        return{
            todos:[
                {id:1,name:"learn vue"},
                {id:2,name:"finish a todo project"},
                {id:3,name:"improve your skills"},
            ]
        }
    },
    methods:{
        DeleteTodo(index){
            this.todos.splice(index,1)
        }
    }

}
</script>

<style scoped>

</style>