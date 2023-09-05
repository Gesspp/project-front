<template>
    <main>
        <div class="add-task">
            <input type="text" v-model="newTask">
            <input type="color" v-model="taskColor">
            <button @click="addTask">+</button>
        </div>
        <div class="tasks">
            <Task v-bind="task" v-for="task in undone" @change-task = "change(tasks.indexOf(task))" @delete-task = "deleteTask(tasks.indexOf(task))"></Task>
            <Task v-bind="task" v-for="task in done" @change-task = "change(tasks.indexOf(task))" @delete-task = "deleteTask(tasks.indexOf(task))"></Task>
        </div>
    </main>
</template>
<script>
    import Task from './Task.vue'
    export default{
        data(){
            return {
                tasks: [
                    {
                        title: "Помыть посуду",
                        done: false,
                        color: "black"
                    },
                    {
                        title: "почистить зубы",
                        done: true,
                        color: "red"
                    }
                ],
                newTask: "",
                taskColor: "#000000"
            }
        },
        components: {
            Task
        },
        methods: {
            addTask(){
                this.tasks.push({title: this.newTask, done: false, color: this.taskColor})
                this.newTask = "";
            },
            change(i){
                this.tasks[i].done = !this.tasks[i].done;
            },
            deleteTask(i){
                this.tasks.splice(i, 1)
            }
        },
        computed: {
            done(){
                return this.tasks.filter(task => task.done)
            },
            undone(){
                return this.tasks.filter(task => !task.done)
            }
        }
    }
</script>
<style>

</style>