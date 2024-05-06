<template>
     <div class="inc-exp-container">
        <div>
          <h4>Income</h4>
          <p id="money-plus" class="money plus">+${{ income }}</p>
        </div>
        <div>
          <h4>Expense</h4>
          <p class="money minus">${{ expenses }}</p>
        </div>
    </div>
</template>


<!-- //NEW WAY TO IMPORT PROPS  -->
<script setup>
const {income, expenses} = defineProps({
  income: {
    type: Number,
    required: true,
  },

  expenses: {
    type: Number,
    required: true,
  }
})
</script>



<!-- //OLD WAY TO IMPORT PROPS  -->

<!-- <script setup>
import { defineProps } from 'vue';

const props = defineProps({
  income: {
    type: Number,
    required: true,
  },

  expenses: {
    type: Number,
    required: true,
  }
})
</script> -->