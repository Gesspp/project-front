<template>
    <button @click="clicks++">{{clicks}}</button>
</template>
<script>
    export default{
        data(){
            return {
                clicks: 0
            }
        }
    }
</script>
<style></style>