<template>
  <div class="annualNetContainer">
    <div class="annualNetLabel">Annual Net</div>
    <div class="annualNetAmount">${{ annualNet }}</div>
  </div>
</template>

<script>
export default {
  props: ["annualNet"],
};
</script>

<style>
.annualNetContainer {
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

.annualNetAmount {
  font-size: 40pt;
}

.annualNetLabel {
  font-size: 20pt;
  color: green;
  font-weight: 800;
  margin-right: 14em;
  margin-bottom: 0.5em;
}
</style>
