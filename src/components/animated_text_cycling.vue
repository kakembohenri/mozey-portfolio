<template>
    <span class="typed">
      {{ typedText }}
    </span>
  </template>
  
  <script>
  export default {
    data() {
      return {
        words: ['Software Developer', 'Front-end Developer', 'GIS Developer / Analysis'],
        currentWordIndex: 0,
        typedText: '',
        typingSpeed: 100, // Adjust the typing speed as needed
      };
    },
    methods: {
      typeWord(word) {
        let index = 0;
        const typeInterval = setInterval(() => {
          this.typedText = word.substring(0, index);
          index++;
  
          if (index > word.length) {
            clearInterval(typeInterval);
  
            // Erase the word after a delay
            setTimeout(() => {
              this.eraseWord(word);
            }, 1000); // Adjust the delay before erasing
  
          }
        }, this.typingSpeed);
      },
      eraseWord(word) {
        let index = word.length;
        const eraseInterval = setInterval(() => {
          this.typedText = word.substring(0, index);
          index--;
  
          if (index < 0) {
            clearInterval(eraseInterval);
  
            // Move to the next word after a delay
            setTimeout(() => {
              this.moveToNextWord();
            }, 500); // Adjust the delay before moving to the next word
          }
        }, this.typingSpeed);
      },
      moveToNextWord() {
        this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
        this.typeWord(this.words[this.currentWordIndex]);
      },
    },
    mounted() {
      this.typeWord(this.words[this.currentWordIndex]);
    },
  };
  </script>
  
  <style scoped>
  /* Add your styling here if needed */
  </style>
  