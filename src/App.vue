<template>
  <div>
    <div class="topRow">
      <AnnualIncome />
      <MonthlyNet />
      <AnnualNet />
    </div>
    <div class="bottomRow">
      <MonthlyExpenses />
      <MonthlyExpenseBreakdown />
    </div>
  </div>
</template>

<script>
import AnnualIncome from "./components/AnnualIncome.vue";
import AnnualNet from "./components/AnnualNet.vue";
import MonthlyExpenseBreakdown from "./components/MonthlyExpenseBreakdown.vue";
import MonthlyExpenses from "./components/MonthlyExpenses.vue";
import MonthlyNet from "./components/MonthlyNet.vue";

export default {
  components: {
    AnnualIncome,
    AnnualNet,
    MonthlyExpenseBreakdown,
    MonthlyExpenses,
    MonthlyNet,
  },
};
</script>

<style>
body {
  background-color: #cfd8dc;
}

.bottomRow {
  display: flex;
  flex-flow: row;
  margin-top: 3em;
  justify-content: space-around;
}

.topRow {
  display: flex;
  flex-flow: row;
  margin-top: 3em;
  justify-content: space-around;
}
</style>
