<script>
import { ref } from 'vue';

export default {
  setup() {
    const accountHolders = ref({ firstName:'', lastName:'', routingNumber:0, balance:0 });

    function createAccountHolder(accountFirstName, accountLastName, accountRoutingNumber, accountBalance) {
      accountHolders.value.firstName = accountFirstName;
      accountHolders.value.lastName = accountLastName;
      accountHolders.value.routingNumber = accountRoutingNumber;
      accountHolders.value.balance = accountBalance;
    }

    createAccountHolder('John', 'Williams', 1723564, 200);

    function deposit(amount) {
      accountHolders.value.balance += amount;
    }

    function withdraw(amount) {
      accountHolders.value.balance -= amount;
    }

    function transfer(amount) {
      accountHolders.value.balance -= amount;
    }

    return {
      accountHolders,
      deposit,
      withdraw,
      transfer
    };
  },
};
</script>

<template>
  <div class="icstarslogo">
    <img src="C:\Users\MonteeEllis\Desktop\Logo ideas\Bank logo.png" alt="bankLogo" width="150">
  </div>
  <nav>
    <h1>Icstars Bank</h1>
  </nav>
  <div class="introduction">Welcome, {{ accountHolders.firstName }} {{ accountHolders.lastName }}</div>
  <br>
  <div class="balance">Balance: {{ accountHolders.balance }}</div>
  <br>
  <div class="money">
    <button @click="deposit(20)">Deposit $20</button>
    <button @click="withdraw(20)">Withdraw $20</button>
  </div>
  <br>
  <div class="transfer"><button @click="transfer(100)">Transfer $100</button></div>
</template>

<style>
</style>
