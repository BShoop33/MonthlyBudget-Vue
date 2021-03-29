<template>
  <div class="monthlyExpensesContainer">
    <div class="monthlyExpensesLabel">Monthly Expenses</div>
    <div class="monthlyExpesesHeaderContainer">
      <div class="monthlyExpensesHeaderName">Name</div>
      <div class="monthlyExpensesHeaderAmount">Amount</div>
    </div>
    <hr style="width: 93%; text-align: left; margin-left: 1" />
    <div class="monthlyExpensesEntriesContainer">
      <div class="monthlyExpensesEntries">
        Entries' Name and Amount PlaceHolder
      </div>
    </div>
    <hr style="width: 93%; text-align: left; margin-left: 1" />
    <div class="addExpenseLabel">Add Expense</div>
    <div class="addExpenseInputContainer">
      <input class="monthlyIncomeNameInput" type="text" />

      <div class="monthlyExpenseInputPrefix">$</div>
      <input class="monthlyIncomeInput" type="number" />
      <button class="monthlyIncomeSubmit">+</button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.monthlyIncomeNameInput {
  font-size: 18pt;
  margin-right: 1em;
  border-left: none;
  border: 1px;
  border-color: black;
  border-style: solid;
  outline: none;
}

.monthlyExpenseInputPrefix {
  border-left: 1px;
  border-left-color: black;
  border-left-style: solid;
  border-bottom: 1px;
  border-bottom-color: black;
  border-bottom-style: solid;
  border-top: 1px;
  border-top-color: black;
  border-top-style: solid;
  padding-left: 0.25em;
  padding-right: 0.25em;
  padding-top: 0.2em;
  margin-left: 1em;
  font-size: 18pt;
}

.monthlyIncomeInput {
  font-size: 18pt;
  margin-right: 1em;
  border-left: none;
  border-right: 1px;
  border-right-color: black;
  border-right-style: solid;
  border-bottom: 1px;
  border-bottom-color: black;
  border-bottom-style: solid;
  border-top: 1px;
  border-top-color: black;
  border-top-style: solid;
  outline: none;
}

.monthlyIncomeSubmit {
  background-color: lightgreen;
  cursor: pointer;
  font-size: 20pt;
  width: 1.35em;
  border-radius: 50em;
  outline: none;
  margin-right: 3em;
}

.addExpenseInputContainer {
  display: flex;
  flex-flow: row;
}

.monthlyExpensesContainer {
  width: 55em;
  height: 30em;
  background-color: white;
  border: 3px;
  border-color: purple;
  border-style: solid;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
}

.monthlyExpensesLabel {
  font-size: 20pt;
  /* margin-bottom: 1em;
  margin-left: 5.5em; */
  color: green;
  font-weight: 800;
  margin-right: 22em;
  /* margin-bottom: 8em; */
}

.monthlyExpesesHeaderContainer {
  display: flex;
  flex-flow: row;
}

.monthlyExpensesHeaderName {
  /* border-bottom: 2px;
  border-bottom-color: black;
  border-bottom-style: solid; */
  width: 17.25em;
  font-weight: 600;
  font-size: 14pt;
  margin-top: 1em;
}

.monthlyExpensesHeaderAmount {
  margin-right: 20.5em;
  /* border-bottom: 2px;
  border-bottom-color: black;
  border-bottom-style: solid; */
  font-weight: 600;
  font-size: 14pt;
  margin-top: 1em;
}

.monthlyExpensesEntries {
  margin-right: 28em;
  overflow: auto;
  width: 20em;
}

.monthlyExpensesEntriesContainer {
  display: flex;
  flex-flow: row;
  height: 16em;
  overflow: auto;
}

.addExpenseLabel {
  font-weight: 600;
  font-size: 14pt;
  margin-right: 38em;
  margin-bottom: 0.5em;
}
</style>