<template src="./template.html"/>

<script>
    import KanbanCard from "@/components/KanbanCard/KanbanCard";

    export default {
        name: "V-KanbanBoard",
        props:["elementIndex","data", 'lastBoard','firstBoard'],
        components: {KanbanCard},
        methods:{
            addButtonClick(){
                this.$emit('addButtonClick');
            },
            notifyHandler(eventName, taskId){
                this.$emit(eventName, taskId, this.elementIndex);
            }
        }
    }
</script>

<style scoped src="./style.less" lang="less"></style>

