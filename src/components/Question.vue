<template>
  <v-container>
    <v-form>
      {{ question }}
      <v-checkbox
        v-for="(answer, index) in answers"
        :key="index"
        v-model="disabled"
        :class=getClass(index)
        :label=answer.value
      ></v-checkbox>
      <v-btn @click="checkAnswers">Check</v-btn>
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: 'Question',

  data: () => ({
    checked: false,
    question: 'What is Your Name?',
    answers: [{
      value: 'Bogdan',
      correct: true,
    }, {
      value: 'Andrei',
      correct: false,
    }, {
      value: 'George',
      correct: false,
    }]
  }),

  methods: {
    checkAnswers() {
      window.alert('altceva');
    },

    getClass(answer) {
      return 'green';
    }
  }
};
</script>
