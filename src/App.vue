<template>
  <h1> Learn Vue </h1>
  <div class="row">
    <div class="col-3"></div>
    <div class="col-6">
      <select v-model="seletedValue" style="margin-bottom: 20px"
              class="form-select" aria-label="Default select example"
              >
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>

<!--      Square of selected value: {{double}}-->

<!--      display this from Double component-->
      <DoubleComponent :original="seletedValue" />
    </div>
    <div class="col-3"></div>

  </div>
</template>

<script>

import DoubleComponent from "./components/DoubleComponent";
export default {
  name: 'App',
  components: {
    DoubleComponent
  },
  data() {
    return {
      seletedValue: 2,
      double: 2*2
    }
  },
  methods: {
    computeSquare(){
      console.log('seletedValue', this.seletedValue);
      this.double = this.seletedValue * this.seletedValue;
    }
  },
  watch: {
    seletedValue: function (newValue, oldValue) {
      console.log("oldValue", oldValue)
      console.log("newValue", newValue)
      this.double = newValue*newValue
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
