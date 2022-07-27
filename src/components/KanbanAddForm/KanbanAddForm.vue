<template src="./template.html"/>

<script>
    export default {
        name: "V-KanbanAddForm",
        props: ['indexTask'],
        beforeMount(){
            this.task = {...this.defaultTask}
        },
        data() {
            return {
                task:null,
                defaultTask:{
                    title: "",
                    deadline: ''
                }
            }
        },
        methods:{
            closeForm(){
                this.task = null;
                this.$emit('close');
            },
            addTask(){
                this.$emit('addTask',{id:this.indexTask,...this.task});
                this.task = null;
                this.closeForm()
            }
        }
    }
</script>

<style scoped lang="less" src = "./style.less">

</style>

