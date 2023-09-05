<template>
    <input type="number" class="number1" v-model="firstNumber">
    <select id="sum-and-other" v-model="action">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
    </select>
    <input type="number" class="number2" v-model="secondNumber">
    <button class="make-an-action" @click="calc">action</button>
    <p class="result">{{result}}</p>
</template>
<script>
    export default{
        data(){
            return {
                firstNumber: 0,
                secondNumber: 0,
                action: 0,
                result: 0
            }
        },
        methods: {
            calc(){
                switch(this.action){
                    case '+': 
                        this.result = this.firstNumber + this.secondNumber;
                        break;
                    case '-': 
                        this.result = this.firstNumber - this.secondNumber;
                        break;
                    case '*': 
                        this.result = this.firstNumber * this.secondNumber;
                        break;
                    case '/': 
                        this.result = this.firstNumber / this.secondNumber;
                        break;

                }
            }
        }
    }
</script>
<style></style>