<template>
  <div class="relative transactions trans-animation group">
    <div>
      <button
        class="delete-btn absolute px-2 bg-red-400 text-white h-full flex items-center rounded-l transition-ease-in-out duration-100"
        @click="deleteTransaction(id)"
      >
        <i class="fa fa-trash"></i>
      </button>
    </div>
    <div
      v-if="amount >= 0"
      class="border-primary border-r-4 p-2 mt-2 shadow bg-white flex justify-between text-sm rounded relative z-10 group-hover:text-red-400"
    >
      <span class="font-semibold text-capitalize">{{ name }}</span>
      <span class="font-semibold"> {{ amount }}</span>
    </div>
    <div
      v-else
      class="border-red-600 border-r-4 p-2 mt-2 shadow bg-white flex justify-between text-sm rounded relative z-10 group-hover:text-red-400"
    >
      <span class="font-semibold text-capitalize">{{ name }}</span>
      <span class="font-semibold"> {{ amount }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Transaction",
  props: {
    name: String,
    amount: Number,
    transactions: Array,
    id: Number,
  },
  methods: {
    deleteTransaction: function (id) {
      // console.log(id);
      this.transactions.splice(0, id);
    },
  },
};
</script>

<style>
</style>