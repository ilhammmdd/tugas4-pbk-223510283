<template>
  <div class="container">
    <h1>StarBoy</h1>
    <p class="tulis">{{ message }}</p>
    <Slot @message-from-child="handleMessageFromChild">
      <template v-slot:additionalContent>
        <p class="tuliss">The Weeknd, Daft Punk</p>
      </template>
    </Slot>
  </div>
</template>

<script>
import Slot from './Slot.vue';

export default {
  components: {
    Slot,
  },
  data() {
    return {
      message: '',
    };
  },
  methods: {
    handleMessageFromChild(payload) {
      this.message = payload;
      this.$emit('message-to-parent', payload); 
    },
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
p {
  font-weight: bold;
  color: red;
}
.tulis{
  padding-top: 30px;
  color: aliceblue;
}
.tuliss{
  padding-top: 2px;
}


</style>
