<template>
    <h1>Composition API</h1>    
    <div>
        <input type="text" v-model="todoListInput">
        <button @click="addTodoList(todoListInput)"> Add </button>
        <p  v-for="(item, index) in todoList" :key="index">
            <span>{{ item }}</span>
            <button @click="removeTodoList(index)">X</button>
        </p>
    </div>
</template>
<script>
import { ref } from "vue";

export default {
    name: "TodoListComposition",
    setup() {
        let todoList = ref([]);
        let todoListInput = ref(null);
        /** 
        * ---------------TODOLIST FUNCTIONS -----------------
        */
        /**
        * Add Item To List
        * @param input
        */
        let addTodoList = (input) => {
            todoList.value.push(input);
        };
        /**
        * remove Item To List
        * @param index
        */
        let removeTodoList = (index) => {
            todoList.value.splice(index, 1);
        };
        /** 
        * ----------------------------------------------------
        */ 
        return {
            todoListInput,
            todoList,
            addTodoList,
            removeTodoList
        }
    }    
}
</script>
