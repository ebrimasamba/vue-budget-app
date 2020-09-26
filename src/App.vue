<template>
  <div id="app" class="py-5 min-h-screen px-10 bg-back text-white">
    <h1 class="text-center text-xl font-bold uppercase">Vue Budget App</h1>

    <div class="max-w-xl mx-auto">
      <Balance v-bind:transactions="transactions" />
      <IncomeExpense v-bind:transactions="transactions" />
      <TransactionList v-bind:transactions="transactions" />
      <AddTransaction v-bind:transactions="transactions" />
    </div>
  </div>
</template>

<script>
import Balance from "./components/Balance";
import IncomeExpense from "./components/IncomeExpense";
import TransactionList from "./components/TransactionList";
import AddTransaction from "./components/AddTransaction";
export default {
  name: "App",
  components: { Balance, IncomeExpense, TransactionList, AddTransaction },
  data() {
    return {
      transactions: [
        { name: "bread", amount: 2000 },
        { name: "Television", amount: -2000 },
        { name: "Allowance", amount: 2000 },
      ],
    };
  },
};
</script>

<style>
html {
  --primaryColor: #41b984;
}
* {
  font-family: rubik, poppins, ubuntu, nunito, helvetica;
  /* outline: none; */
}

input:focus,
button:focus {
  outline: none !important;
  box-shadow: none !important;
}
/* .text-7xl {
  font-size: 5.5rem;
} */

.bg-teal-gradient {
  background-image: linear-gradient(to left, #41b984, #2c8b62);
}
.bg-red-gradient {
  background-image: linear-gradient(to left, #f06969, #e41313);
}

.bg-back {
  background-image: linear-gradient(#1818189a, #18181871),
    url(./assets/jared-arango-1-mh6U3qeGQ-unsplash.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.text-primary {
  color: var(--primaryColor);
}

.border-primary {
  border-color: var(--primaryColor);
}
.border .delete-btn {
  top: 0;
  left: 0%;
}
.transactions:hover .delete-btn {
  transform: translateX(-100%);
}

.trans-animation {
  animation: fade 0.3s !important;
}

.trans-animation-out {
  animation: fadeOut 0.3s forwards !important;
}

@keyframes fadeOut {
  0% {
    transform: translatex(0), rotate(0deg);
    opacity: 1;
    width: 100%;
  }

  100% {
    transform: translatex(-10%), rotate(20deg);
    width: 0;
    opacity: 0;
  }
}

@keyframes fade {
  0% {
    transform: rotate(20deg);
    width: 0;
    opacity: 0;
  }
  100% {
    transform: rotate(0deg);
    opacity: 1;
    width: 100%;
  }
}
/* .max-h-200 {
  max-height: 200px;
  overflow-y: auto;
  overflow-x: visible;
} */
</style>
