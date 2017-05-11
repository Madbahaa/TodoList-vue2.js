 
<template>
    <div class="todo">
        <h2>To do list </h2>
        <form @submit="addTask">
            <input type="text" v-model="newTask.todo" placeholder="your task here">
            <input type="submit" value="Add Task">
        </form>
        <h6>delete</h6>
        <hr>
        <p v-for="task in tasks" :class="{delete : task.delete, done : task.done}">
            <input type="checkbox" v-model="task.done" :class="{delete : task.delete}">
            <span :class="{delete : task.delete, done : task.done}">
                {{task.todo}}
           <input type="checkbox" class="btn" v-model="task.delete">
          
            </span>
            
            </p>
    </div>
</template>

<script>
    export default {
        name: 'todo',
        data(){
            return {
                newTask: {},
                Tasks : [
                    {
                        todo: '',
                        done: false,
                        delete: false
                    }
                ],
                tasks: [
                    {
                        todo : 'this is one',
                        done: true ,
                        delete: false
                    
                    },
                    {
                        todo : 'ohhh another',
                        done: false,
                        delete: false
                    },
                    {
                        todo : 'third one boy',
                        done: false,
                        delete: false
                    },
                    {
                        todo : 'maybe final one',
                        done: false,
                        delete: false
                    },
                     {
                        todo : 'there is more ',
                        done: false,
                        delete: false
                    },
                     {
                        todo : 'and also more tasks',
                        done: false,
                        delete: false
                    },
                     {
                        todo : 'final one',
                        done: false,
                        delete: false
                    },
                ]
            }
        },
        methods: {
            addTask: function(e){
                this.tasks.push({
                    todo: this.newTask.todo,
                    done: false,
                    delete: false
                });
                e.preventDefault();
            }
        }
        
        
        
    }
</script>

<style scoped>
   .todo {
        font-family: Arial, Helvetica, sans-serif;
        margin: 5px auto;
        width: 320px;
        border : 1px solid #7bc1fd;

    }
    .todo h2 {
        padding: 15px 10px;
        margin-bottom: 15px;
        margin-top: 0px;
        background-color: #125e5e;
        color: white;
        width: 300px ;
        
    }
    .todo p {
        text-align: left;
        padding: 0 10px;
        border-bottom: 1px solid #eee;
        padding: 4px 0 ;
        margin: 0;
    }
    
    input {
        float: left;
    }

    .done {
        text-decoration: line-through;
    }
    .delete {
        display: none;
    }
    
    .btn {
        float: right;
    }

    h6 {
        text-align: right;
    }
    
</style>