<template>
  <div>
    <div class="topRow">
      <AnnualIncome />
      <AnnualNet />
      <MonthlyNet />
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
import MonthlyNet from "./components/MonthlyNet.vue";
import MonthlyExpenses from "./components/MonthlyExpenses.vue";
import MonthlyExpenseBreakdown from "./components/MonthlyExpenseBreakdown.vue";

export default {
  components: {
    AnnualIncome,
    AnnualNet,
    MonthlyNet,
    MonthlyExpenses,
    MonthlyExpenseBreakdown,
  },
};
</script>

<style>
.topRow {
  display: flex;
  flex-flow: row;
  justify-content: space-around;
  margin-top: 2em;
}

.bottomRow {
  display: flex;
  flex-flow: row;
  justify-content: space-around;
  margin-top: 2em;
}
</style>