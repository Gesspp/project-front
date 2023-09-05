<template>
    <input type="color" v-model="color">
    <input type="text" v-model="text" class="reversed-text">
    <h1 :style="{color}">{{reversed}}</h1>
</template>
<script>
    export default{
        data(){
            return {
                text: '',
                color: ''
            };
        }, 
        computed: {
            reversed(){
                return this.text.split('').reverse().join('');
            }
        }
    }
</script>
<style scoped>
    .reversed-text{
        width: 200px;
        height: 40px;
        font-size: 30px;
    }
</style>