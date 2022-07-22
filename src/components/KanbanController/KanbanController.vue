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
                addFormVisible: false

            }
        },
        methods: {
            addTask(taskData) {
                this.boards[0].tasks.push(taskData)
            },
            closeCard() {
                this.addFormVisible = false;
            },
            addButtonClick() {
                this.addFormVisible = true;
            }
        }

    }
</script>

<style scoped src="./style.less" lang="less"></style>

