<template>
  <div>
    <div class="topRow">
      <AnnualIncome />
      <AnnualNet />
      <MonthlyNet />
    </div>
    <div class="bottomRow">
      <MonthlyExpenses
        @input-submit="submitNewExpense"
        :inputs="inputs"
        @expense-removed="handleExpenseRemoved"
      />
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
  data() {
    return {
      inputs: [],
    };
  },
  mounted() {
    const existingInputs = JSON.parse(localStorage.getItem("expenseEntry"));
    this.inputs = existingInputs || [];
  },
  methods: {
    submitNewExpense(newEntry) {
      this.inputs.push(newEntry);
      console.log(this.inputs);
      localStorage.setItem("expenseEntry", JSON.stringify(this.inputs));
    },
    handleExpenseRemoved(expenseToRemove) {
      this.inputs = this.inputs.filter((e) => {
        return e !== expenseToRemove;
      });
      localStorage.setItem("monthlyExpenses", JSON.stringify(this.inputs));
    },
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