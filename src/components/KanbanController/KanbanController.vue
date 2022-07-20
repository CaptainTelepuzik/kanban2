<template src="./template.html"/>

<script>
    import KanbanBoard from "@/components/KanbanBoard/KanbanBoard";
    import KanbanAddForm from "@/components/KanbanAddForm/KanbanAddForm";

    export default {
        name: "V-KanbanController",
        components:{
          KanbanBoard, KanbanAddForm
        },
        data() {
            return {
                boards: [
                    {
                        title: "В ожидании",
                        background: '#eee',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "В работе",
                        background: '#eee',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "Тестирование",
                        background: '#eee',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "Выполнено",
                        background: '#eee',
                        cardBackground: '#eee',
                        tasks: []
                    },
                ],
                addFormVisible: false

            }
        },
        methods:{
            addTask: {
                addTask(taskData){
                    this.boards[0].tasks.push(taskData)
                },
                closeCard(){
                    this.addFormVisible=false;
                }
            }
        }

    }
</script>

<style scoped src="./style.less" lang="less"></style>

