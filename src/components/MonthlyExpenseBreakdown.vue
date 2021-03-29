<template>
  <div class="monthlyExpenseBreakdownContainer">
    <div class="monthlyExpenseBreakdownLabel">Monthly Expense Breakdown</div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.monthlyExpenseBreakdownContainer {
  width: 55em;
  height: 40em;
  background-color: white;
  border: 3px;
  border-color: purple;
  border-style: solid;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
}

.monthlyExpenseBreakdownLabel {
  font-size: 20pt;
  color: green;
  font-weight: 800;
  margin-right: 18em;
  margin-bottom: 20em;
}
</style>
