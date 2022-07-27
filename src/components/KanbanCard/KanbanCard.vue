<template src="./template.html"/>
<script>
    export default {
        name: "V-KanbanCard",
        props:['color','data','elementIndex','last','first'],
        methods:{
            notifyHandler(eventName){
                this.$emit(eventName,this.data.id);
            }
        }

    }
</script>

<style scoped src="./style.less" lang="less"></style>

