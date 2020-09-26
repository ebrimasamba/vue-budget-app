<template>
  <div>
    <form action="">
      <h3 class="font-semibold border-b pb-1 text-lg mt-3">
        Add new transaction
      </h3>
      <div class="mt-5">
        <div class="text-sm">
          <label for="name" class="block font-semibold mb-1"> Name </label>
          <input
            type="text"
            class="form-input w-full p-3 shadow rounded-md text-sm text-black"
            placeholder="name of transaction"
            v-model="name"
            id="name"
          />
        </div>
        <div class="mt-3 text-sm">
          <label for="amount" class="block font-semibold mb-1"> Amount </label>
          <input
            type="number"
            class="form-input w-full p-3 shadow rounded-md text-sm text-black"
            placeholder="negative-expense positive-income"
            id="amount"
            v-model="amount"
          />
        </div>
        <button
          class="mt-4 w-full py-3 bg-blue-600 text-white font-semibold rounded-md shadow uppercase border-b-4 border-blue-700"
          @click="addTransaction"
        >
          Add Transaction
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTransaction",
  props: {
    transactions: Array,
  },
  data() {
    return {
      name: "",
      amount: 0,
    };
  },
  methods: {
    addTransaction: function (e) {
      e.preventDefault();
      let newTransaction = { name: this.name, amount: Number(this.amount) };
      this.transactions.push(newTransaction);
      console.log(this.transactions);
      this.name = "";
      this.amount = 0;
    },
  },
};
</script>

<style>
</style>