<template>
  <div>
    <div class="text-center mt-3">
      <h4 class="uppercase text-sm">Your Balance</h4>
      <p class="font-semibold text-2xl">
        D{{
          transactions.reduce(
            (acc, currValue) => acc + Number(currValue.amount),
            0
          )
        }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Balance",
  props: {
    transactions: Array,
  },
  mounted() {},
};
</script>

<style>
</style>