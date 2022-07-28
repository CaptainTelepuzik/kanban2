<template src="./template.html"/>

<script>
    import KanbanBoard from "@/components/KanbanBoard/KanbanBoard";
    import KanbanAddForm from "@/components/KanbanAddForm/KanbanAddForm";

    export default {
        name: "V-KanbanController",
        components: {
            KanbanBoard, KanbanAddForm
        },
        data() {
            return {
                boards: [
                    {
                        title: "В ожидании",
                        background: '#dc7373',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "В работе",
                        background: '#5674bb',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "Тестирование",
                        background: '#dbc75d',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: "Выполнено",
                        background: '#81d414',
                        cardBackground: '#eee',
                        tasks: []
                    },
                ],
                addFormVisible: false,
                indexTask:0

            }
        },
        methods: {
            addTask(taskData) {
                this.indexTask++
                this.boards[0].tasks.push(taskData)
            },
            closeCard() {
                this.addFormVisible = false;
            },
            addButtonClick() {
                this.addFormVisible = true;
            },
            deleteTask(taskId, boardId){
                const tasks = this.boards[boardId].tasks;
                const newTasks = [];

                tasks.forEach((item)=>{
                    if (item.id !== taskId) {
                        newTasks.push(item);
                    }
                });

                this.boards[boardId].tasks= newTasks;
            },
          moveNextBoard(taskId, boardId) {
            const tasks = this.boards[boardId].tasks;
            const newTasks = [];
            let itemNew = null;

            tasks.forEach((item) => {
              if (item.id !== taskId) {
                newTasks.push(item);
              } else {
                itemNew = item;
              }
            });
            this.boards[boardId + 1].tasks.push(itemNew);
            this.boards[boardId].tasks = newTasks;
          },
          movePrevBoard(taskId, boardId) {
            const tasks = this.boards[boardId].tasks;
            const newTasks = [];
            let itemNew = null;

            tasks.forEach((item) => {
              if (item.id !== taskId) {
                newTasks.push(item);
              } else {
                itemNew = item;
              }
            });
            this.boards[boardId - 1].tasks.push(itemNew);
            this.boards[boardId].tasks = newTasks;
          }
        }

    }
</script>

<style scoped src="./style.less" lang="less"></style>

