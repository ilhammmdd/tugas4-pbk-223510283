<template>
  <div id="app">
    <Emit @message-to-parent="handleMessageFromEmit" />
  </div>
</template>

<script>
import Emit from './components/Emit.vue';

export default {
  components: {
    Emit,
  },
  methods: {
    handleMessageFromEmit(payload) {
      console.log('Message from Emit:', payload);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #020202;
  background-image: url('https://i.scdn.co/image/ab67616d00001e028863bc11d2aa12b54f5aeb36');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  height: 50vh; 
}

body {
  background-color: #e3e3e3;
  margin: 0; 
}
</style>
