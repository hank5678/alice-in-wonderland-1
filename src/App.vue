<template>
  
  <span>{{num1}}+{{num2}}=</span>
<input v-model="userAnswer" type="text">
<button @click="checkanswer">送出</button>
</template>


<!-- <script>
export default {
  data() {
    return {
      num1:Math.floor(Math.random()*9)+1,
      num2:Math.floor(Math.random()*9)+1,
      userAnswer:''
    };
  },
  methods: {
    checkanswer() {
      if(this.num1+this.num2 == this.userAnswer) {
        alert('正確');
        this.userAnswer = '';
        this.num1=Math.floor(Math.random()*9)+1;
        this.num2=Math.floor(Math.random()*9)+1;
      }
    }
  },
};
</script> -->

<script setup>
import {ref} from 'vue'

 let num1=ref(Math.floor(Math.random()*9)+1)
 let num2=ref(Math.floor(Math.random()*9)+1)
 let answer=ref(0);
 let userAnswer = ref('');

 function checkanswer(){
  answer.value=num1.value+num2.value
  if(userAnswer.value==answer.value){
    alert("正確")

  num1.value=Math.floor(Math.random()*9)+1
  num2.value=Math.floor(Math.random()*9)+1
  userAnswer.value = ''
  }
  else{
    alert("錯誤")
  }

 }
</script>

<style scoped>
</style>
