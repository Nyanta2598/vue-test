<template> 
    <h1>Options API</h1>
    <div>
        <form v-on:submit.prevent="addTodoList(todoListInput)">
            <input type="text" v-model="todoListInput" />
            <button style="margin-left: 10px" > Add </button>
            <p v-for="(item, index) in todoList" :key="index">
                <span>{{item}}</span>
                <button style="margin-left: 10px" @click="removeTodoList(index)">X</button>
            </p>
        </form>
    </div>
</template>

<script>
export default {
    name: "OptionComponents",
    data(){
        return{
            todoListInput: null,
            todoList: []
        }
    },
    methods: {
        addTodoList(input){
            this.todoList.push(input)
        },
        removeTodoList(index) {
            this.todoList.splice(index, 1);
        }
    }
}
</script>