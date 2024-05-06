<template>
     <h3>History</h3>
      <ul class="list">
            <li v-for="transaction in transactions" v-bind:key="transactions.id"
            :class="transaction.amount <0 ? 'minus' : 'plus'"
            >
                {{ transaction.text }}<span>${{transaction.amount}}</span>
                <button @click="deleteTransaction(transaction.id)" class="delete-btn">x</button>
            </li>

            <!-- <li class="minus">
                Cash <span>-$400</span><button class="delete-btn">x</button>
            </li>
            <li class="plus">
                Paycheck <span>$400</span><button class="delete-btn">x</button>
            </li> -->
      </ul>
</template> 


<!-- Composition API -->
<script setup>
import { defineEmits } from 'vue';

const emit = defineEmits(['transactionDeleted'])

const { transactions } = defineProps({
    transactions: {
        type: Array,
        required: true,
    }
});

const deleteTransaction = (id) => {
    emit('transactionDeleted', id)

}
</script>

<!-- Option API -->
<!-- <script>
    export default {
        data() {
            return {
                transactions: [
                    {id: 1, text: 'flowers', amount: -19.99},
                    {id: 2, text: 'salary', amount: 200.09},
                    {id: 3, text: 'books', amount: -10},
                    {id: 4, text: 'camera', amount: 150},
                ]
            };
        },
    };
</script> -->