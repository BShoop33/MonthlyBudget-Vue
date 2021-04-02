<template>
  <div class="monthlyNetContainer">
    <div class="monthlyNetLabel">Monthly Net</div>
    <div class="monthlyNetAmount">{{ monthlyNet }}</div>
  </div>
</template>

<script>
export default {
  props: ["monthlyNet"],
  // methods: {
  // showIncome() {
  //   const annualIncome = JSON.parse(localStorage.getItem("annualIncome"));
  //   this.income = annualIncome || [];
  // },
  // },
};
</script>

<style>
.monthlyNetContainer {
  width: 35em;
  height: 9em;
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-flow: column;
  border: 3px;
  border-color: purple;
  border-style: solid;
}

.monthlyNetAmount {
  font-size: 40pt;
  /* margin-bottom: 1em;
  margin-left: 5.5em; */
}

.monthlyNetLabel {
  font-size: 20pt;
  /* margin-bottom: 1em;
  margin-left: 5.5em; */
  color: green;
  font-weight: 800;
  margin-right: 14em;
  margin-bottom: 0.5em;
}
</style>
