<script setup>
import { ref } from 'vue'

defineProps({
  question: String,
  answer1: String,
  answer2: String

})
// here we put to define the one choice

const emit = defineEmits([
  'answer-selected'
])

const choice = ref('')

function choiceMade() {
  //emit event to tell parent what choice the user has made.
  emit('answer-selected', choice.value)
}


</script>

<template>

  <div id="wyr">

    <h2>Make your choice!</h2>

    <p>{{ question }}</p>

    <div>

    <input v-model="choice" v-bind:value="answer1" v-on:change="choiceMade" type="radio" id="answer-1">
    <label for="answer-1">{{ answer1 }}</label>

    <input v-model="choice" v-bind:value="answer2" v-on:change="choiceMade" type="radio" id="answer-2">
    <label for="answer-2"> {{ answer2 }}</label>

</div>

</div>
  
</template>

<style scoped>

#wyr{
  background-color: aqua;
}

p{
  font-family: fantasy;
}
</style>
