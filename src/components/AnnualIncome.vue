<template>
  <div class="annualIncomeContainer">
    <div class="annualIncomeLabel">Annual Income</div>
    <v-form
      class="annualIncomeInputContainer"
      @submit.prevent="handleSubmit"
      ref="contactForm"
    >
      <div class="annualIncomeInputPrefix">$</div>
      <input
        class="annualIncomeInput"
        type="number"
        @submit.prevent="handleSubmit"
        ref="firstName"
      />
    </v-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        firstName: "",
      },
    };
  },
  methods: {
    handleSubmit() {
      console.log("go");

      this.$refs.firstNameInput.value = "";
    },
  },
};
</script>

<style scoped>
.annualIncomeInputContainer {
  display: flex;
  flex-flow: row;
}

.annualIncomeContainer {
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

.annualIncomeInputPrefix {
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
}

.annualIncomeInput {
  font-size: 20pt;
  width: 18em;
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

.annualIncomeInputPrefix {
  font-size: 20pt;
}

.annualIncomeLabel {
  font-size: 20pt;
  margin-right: 5.5em;
  font-weight: 800;
  color: green;
  margin-bottom: 1em;
  margin-right: 12em;
}
</style>
