<template>
    <div class="gtu">
      <h2>Push Button</h2><br />
      <Button @message-from-grandchild="haha" />
      <slot name="additionalContent"></slot>
    </div>
  </template>
  
  <script>
  import Button from './Button.vue';

  export default {
    components: {
      Button,
    },
    methods: {
      haha(payload) {
        this.$emit('message-from-child', payload);
      },
    },
  };
  </script>
  
  <style scoped>
  .gtu {
    margin-top: 5px;
    padding-bottom: 20px;

  }
  h2{
    color: white;
    
  }
  </style>
  
  