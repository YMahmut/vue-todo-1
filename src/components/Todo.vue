<template>
    <div id="todo">
        <div class="row">
            <div class="col">
                <ul style="padding: 0px ;margin: 0px">
                    <TransitionGroup name="list" tag="ul">
                        <li class="m-2 p-2" v-for="(todo,index) in todos" :key="todo.id">
                            <span @click="todo.isDone=!todo.isDone" :class="{done:todo.isDone}" class="col-md todos">{{todo.name}}</span>
                            <span>
                                <button class="col-xs m-2 p-2 del-button"  @click="DeleteTodo(index)">Delete</button>
                            </span>
                        </li>
                    </TransitionGroup>
                </ul>
            </div>
            <div class="col">
                <NewTodo class="m-5 p-3" @sendNewToDo="todos.push({id:todos.length+1, name:$event})"/>
            </div>
        </div>

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
            lined:false,
            todos:[
                {id:1,name:"learn vue js", isDone:false},
                {id:2,name:"finish a todo project", isDone:false},
                {id:3,name:"improve your skills", isDone:false},
            ]
        }
    },
    methods:{
        DeleteTodo(index){
            this.todos.splice(index,1)
        },
    }

}
</script>

<style scoped>
#todo{
    position: relative;
    width: 100%;
}
li{
    list-style: none;
    background-color: #c57272;
    border-radius: 5px;
    box-shadow: 1px 2px 3px #000;
    display: flex;
    flex-direction: row;
}
.todos{
    margin-right: 50px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: start;
    position: relative;
    width: 87%;
    user-select: none;
}
.del-button{
    border: none ;
    border-radius: 5px;
    background-color: #f3ebeb;
}
li>span{
    flex-direction: column;
    text-align: start;
}
.done{
    text-decoration-line:line-through;
    text-decoration-color: #e3b6ba;
}
.list-enter-active,
.list-leave-active {
    transition: all 0.75s ease;
}
.list-enter-from,
.list-leave-to {
    opacity: 0;
    transform: translateX(40px);
}
</style>