<template>
  <div>
    <div class="flex justify-center mt-2 rounded-md text-sm">
      <div
        class="bg-teal-gradient bg-tel-500 text-gray-100 text-center w-1/2 rounded-md p-3 relative shadow"
      >
        <div class="relative z-10">
          <h5 class="uppercase font-bold tracking-widest">Income</h5>
          <span class="text font-bold text-lg md:text-xl">
            D{{
              Intl.NumberFormat().format(
                Math.abs(
                  newIncome.reduce(
                    (acc, currValue) => acc + Number(currValue.amount),
                    0
                  )
                )
              )
            }}
          </span>
        </div>
        <i
          class="fas fa-money-bill absolute text-primary text-4xl top-5 left-3 hidden md:block"
        ></i>
      </div>
      <div
        class="bg-red-gradient bg-red-600 text-gray-100 text-center w-1/2 rounded-md p-3 relative ml-2 shadow"
      >
        <div class="relative z-10">
          <h5 class="uppercase font-bold tracking-widest">Expenses</h5>
          <span class="tex font-bold text-lg md:text-xl">
            -D{{
              Intl.NumberFormat().format(
                Math.abs(
                  newExpenses.reduce(
                    (acc, currValue) => acc + Number(currValue.amount),
                    0
                  )
                )
              )
            }}
          </span>
        </div>
        <i
          class="fas fa-shopping-bag absolute text-red-500 text-4xl top-5 left-3 hidden md:block"
        ></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IncomeExpense",
  props: { transactions: Array },
  computed: {
    newIncome() {
      return this.transactions.filter((value) => value.amount >= 0);
    },
    newExpenses() {
      return this.transactions.filter((value) => value.amount < 0);
    },
  },
};
</script>

<style></style>
