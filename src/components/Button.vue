<template>
  <div class="container">
    <button @click="playMusic" class="play-button"></button>
    <audio id="myAudio" :src="audioSrc" preload="auto"></audio>
  </div>
</template>

<script>
export default {
  data() {
    return {
      audioSrc: './music.mp3',
    };
  },
  methods: {
    playMusic() {
      const audio = document.getElementById('myAudio');
      audio.play();
      this.$emit('message-from-grandchild','Music Played'); 
    },
  },
};
</script>

<style scoped>
.play-button {
  padding: 1rem 2rem;
  border: none;
  background-color: #e8ecf9;
  background-image: url('https://static.thenounproject.com/png/72324-200.png');
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  color: rgb(29, 28, 31);
  cursor: pointer;
}

.play-button:hover {
  background-color: red;
  transition: 0.5ms;
}
</style>
