<template>
  <div class="mt-5">
    <h3 class="font-semibold border-b pb-1 text-lg">Transactions</h3>
    <div class="text-black" v-if="transactions.length > 0">
      <div v-bind:key="trans.id" v-for="(trans, id) in transactions">
        <Transaction
          v-bind:name="trans.name"
          v-bind:amount="trans.amount"
          v-bind:transactions="transactions"
          :id="id"
        />
      </div>
    </div>
    <div v-else>
      <p>No new transactions</p>
    </div>
  </div>
</template>

<script>
import Transaction from "./Transaction";
export default {
  name: "TransactionList",
  components: { Transaction },
  props: {
    transactions: Array,
  },
};
</script>

<style>
</style>