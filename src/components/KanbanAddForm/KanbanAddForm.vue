<template src="./template.html"/>

<script>
    export default {
        name: "V-KanbanAddForm",
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
                this.$emit('addTask',{...this.task});
                this.task = null;
            }
        }
    }
</script>

<style scoped lang="less" src = "./style.less">

</style>

