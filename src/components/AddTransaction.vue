<template>
    <h3>Add new transaction</h3>
      <form @submit.prevent="onSubmit">
            <div class="form-control">
                <label for="text">Text</label>
                <input type="text" v-model="text" placeholder="Enter text..." />
            </div>
            <div class="form-control">
                <label for="amount"
                >Amount 
                (negative - expense, positive - income)</label>
                <input type="text"  v-model="amount" placeholder="Enter amount..." />
            </div>
            <button type="submit" class="btn">Add transaction</button>
      </form>
</template>

<script setup>
import { ref, defineEmits } from 'vue';
import { useToast } from 'vue-toastification'

const text = ref('');
const amount = ref('');

const emit = defineEmits(['transactionSubmitted']);

// Get toast interface
const toast = useToast();

const onSubmit = () => {
     // Display a toast error message if either field is empty
    if(!text.value || !amount.value){
        toast.error('both field must be filled');
        return;
    }

    const transactionData = {
        text: text.value,
        amount: parseFloat(amount.value),
    };

    emit('transactionSubmitted', transactionData);

     // Clear form fields
    text.value = '';
    amount.value = '';
}
</script>