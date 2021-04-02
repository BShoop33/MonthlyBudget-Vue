<template>
  <v-card>
    <div class="monthlyExpensesContainer">
      <div class="monthlyExpensesLabel">Monthly Expenses</div>
      <div class="monthlyExpesesHeaderContainer">
        <div class="monthlyExpensesHeaderName">Name</div>
        <div class="monthlyExpensesHeaderAmount">Amount</div>
      </div>
      <hr style="width: 93%; text-align: left; margin-left: 1" />
      <div class="monthlyExpensesEntriesContainer">
        <v-card-text>
          <v-simple-table>
            <template v-slot:default>
              <tbody class="table">
                <tr v-for="input in inputs" :key="input.monthlyIncomeNameInput">
                  <td class="monthlyIncomeNameEntry">
                    {{ input.name }}
                  </td>
                  <td class="monthlyIncomeAmountEntry">
                    {{ input.amount }}
                  </td>
                  <td class="text-right">
                    <v-btn fab x-small dark @click="handleRemove(input)">
                      <v-icon class="deleteIcon">mdi-minus</v-icon>
                    </v-btn>
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-card-text>
      </div>
      <hr style="width: 93%; text-align: left; margin-left: 1" />
      <v-form
        class="MonthlyExpensesInputContainer"
        @submit.prevent="handleSubmit"
      >
        <div class="addExpenseLabel">Add Expense</div>

        <div class="addExpenseInputContainer">
          <div class="monthlyExpenseInputPrefix"></div>
          <input
            class="monthlyIncomeNameInput"
            v-model="form.monthlyIncomeNameInput"
            type="text"
            ref="monthlyIncomeNameInput"
          />

          <div class="monthlyExpenseInputPrefix">$</div>
          <input
            class="monthlyIncomeInput"
            v-model="form.monthlyIncomeAmountInput"
            type="number"
            ref="monthlyIncomeAmountInput"
          />
          <button class="monthlyIncomeSubmit" type="submit">+</button>
        </div>
      </v-form>
    </div>
  </v-card>
</template>

<script>
export default {
  props: ["inputs"],
  data() {
    return {
      form: {
        monthlyIncomeNameInput: "",
        monthlyIncomeAmountInput: 0,
      },
    };
  },

  methods: {
    handleSubmit() {
      this.$emit("input-submit", {
        name: this.form.monthlyIncomeNameInput,
        amount: +this.form.monthlyIncomeAmountInput,
      });
      // this.$emit("input-submit", this.form);
      this.$refs.monthlyIncomeNameInput.value = "";
      this.$refs.monthlyIncomeAmountInput.value = null;
    },
    handleRemove(expense) {
      this.$emit("expense-removed", expense);
    },
  },
};
</script>

<style>
.deleteButton {
  background-color: red;
  border-radius: 50px;
  outline: none;
}

.monthlyIncomeNameEntry {
  width: 23em;
}
.monthlyIncomeAmountEntry {
  width: 30em;
}

.monthlyExpensesContainer {
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

.monthlyExpensesLabel {
  font-size: 20pt;
  color: green;
  font-weight: 800;
  margin-right: 22em;
}

.table {
  width: 40em;
}

.entries {
  display: flex;
  flex-flow: row;
  margin-bottom: 1em;
  font-size: 14pt;
}

.monthlyIncomeAmount {
  margin-left: 16em;
}

.monthlyIncomeNameInput {
  font-size: 18pt;
  margin-right: 1em;
  border-left: none;
  border: 1px;
  border-color: black;
  border-style: solid;
  outline: none;
  border-left: none;
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

.monthlyExpesesHeaderContainer {
  display: flex;
  flex-flow: row;
}

.monthlyExpensesHeaderName {
  width: 17.25em;
  font-weight: 600;
  font-size: 14pt;
  margin-top: 1em;
}

.monthlyExpensesHeaderAmount {
  margin-right: 20.5em;
  font-weight: 600;
  font-size: 14pt;
  margin-top: 1em;
  margin-bottom: 1em;
}

.monthlyExpensesEntries {
  overflow: auto;
  width: 42em;
  margin-top: 1em;
  /* display: flex;
  flex-flow: row;
  margin-bottom: 1em;
  font-size: 14pt; */
}

.monthlyExpensesEntriesContainer {
  display: flex;
  flex-flow: row;
  height: 25em;
  overflow: auto;
}

.addExpenseLabel {
  font-weight: 600;
  font-size: 14pt;
  margin-right: 38em;
  margin-bottom: 0.5em;
}
</style>
