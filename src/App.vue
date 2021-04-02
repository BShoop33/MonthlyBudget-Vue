<template>
  <div>
    <div class="topRow">
      <AnnualIncome @annualExpenseSubmitted="showIncome" />
      <AnnualNet />
      <MonthlyNet :monthlyNet="monthlyNet" />
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
      monthlyNet: 0,
      annualIncome: 0,
    };
  },
  mounted() {
    const existingInputs = JSON.parse(localStorage.getItem("monthlyExpenses"));
    this.inputs = existingInputs || [];
  },
  methods: {
    submitNewExpense(newEntry) {
      this.inputs.push(newEntry);
      localStorage.setItem("monthlyExpenses", JSON.stringify(this.inputs));
    },
    handleExpenseRemoved(expenseToRemove) {
      this.inputs = this.inputs.filter((e) => {
        return e !== expenseToRemove;
      });
      localStorage.setItem("monthlyExpenses", JSON.stringify(this.inputs));
    },
    showIncome() {
      this.annualIncome = JSON.parse(localStorage.getItem("annualIncome"));
      this.monthlyNet = this.annualIncome - this.totalMonthlyExpenses;
      // this.form.annualIncome - this.totalMonthlyExpenses;
    },
  },
  computed: {
    //   monthlyIncome() {
    //     return this.annualIncome / 12;
    //   },
    totalMonthlyExpenses() {
      return this.inputs.reduce((total, month) => {
        return total + month.amount;
      }, 0);
    },
    //   annualExpenses() {
    //     return this.totalMonthlyExpenses * 12;
    //   },
    //   monthlyNet() {
    //     return (this.monthlyIncome - this.totalMonthlyExpenses).toFixed(2);
    //   },
    //   annualNet() {
    //     return +(this.annualIncome - this.annualExpenses).toFixed(2);
    //   },
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