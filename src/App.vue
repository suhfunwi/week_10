<script setup>
import WouldYouRather from './components/WouldYouRather.vue'
import {ref} from 'vue'
const wyrQuestion = ref('Would you rather have ninja-like skills or have amazing coding skills in any language?')
const wyrAnswer1 = ref('Ninja-like skills')
const wyrAnswer2 = ref('Amazing coding skills')
// just the questions and the options for answers

const userSelection = ref('')
//this sill store the user's answer once they make a choice
function updateUserSelection(userChoice){
  userSelection.value = `You chose ${userChoice}!`
// '${}' is a template string, don't forget
}


</script>

<template>
  <div id="app-component">
  <h1>Would You Rather?</h1>
    <WouldYouRather v-bind:question="wyrQuestion"
                    v-bind:answer1="wyrAnswer1"
                    v-bind:answer2="wyrAnswer2"
                    v-on:answer-selected="updateUserSelection"
    ></WouldYouRather>
  <!--  sends the would you rather data to the WouldYouRather prop-->

    <p>{{userSelection}}</p>
  </div>
</template>

<style scoped>
#app-component{
  //font-size: 3em;
  background-color: dodgerblue;
  padding: 40px;
}
p{
  font-family: "Franklin Gothic Medium",serif;
}

</style>
