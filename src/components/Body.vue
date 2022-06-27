<template>
    <div id="card-body">
        <b-card >
            <appHeader/>
            <Todo/>
        </b-card>
    </div>
</template>

<script>
import appHeader from "./Header"
import ToDo from "./Todo";
export default {
    name: "appBody",
    components:{
        appHeader:appHeader,
        Todo:ToDo,
    }
}
</script>

<style scoped>
#card-body{
    background-color: #d9bcbc;
    padding: 20px;
    margin: 10px;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    text-align: center;
    height: 90vh;
}
</style>