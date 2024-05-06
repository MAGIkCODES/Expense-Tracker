<template>
    <h4>Your Balance</h4>
    <h1>₦{{ total }}</h1>
</template>


<!-- //NEW WAY TO IMPORT PROPS  -->

<script setup>

const { total } = defineProps({
  total: {
    type: Number,
    required: true
  }
});
</script>


<!--   OLD WAY -->

<!-- <script setup>
import { defineProps } from 'vue';

const props = defineProps({
    total: {
        type: Number,
        required: true,
    }
})
</script> -->



<!-- ANOTHER WAY TO STRUCTURE THIS CODE  -->

<!-- <template>
    <h4>Your Balance</h4>
    <h1>₦{{ props.total }}</h1>
  </template>
  
  <script setup>
  const props = defineProps({
    total: {
      type: Number,
      required: true
    }
  });
  </script> -->