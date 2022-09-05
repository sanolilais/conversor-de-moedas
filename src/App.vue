<template>
  <div id="app">
    <div class="line">
      <Conversor moeda-a="USD" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="USD"  />
    </div>
    <div class="line">
      <Conversor moeda-a="EUR" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="EUR"  />
    </div>
    <div class="line">
      <Conversor moeda-a="ARS" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="ARS"  />
    </div>
    <div class="line">
      <Conversor moeda-a="JPY" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="JPY"  />
    </div>
    <div class="line">
      <Conversor moeda-a="CNY" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="CNY"  />
    </div>
    <div class="line">
      <Conversor moeda-a="RUB" moeda-b="BRL"  />
      <Conversor moeda-a="BRL" moeda-b="RUB"  />
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"
export default {
  name: 'App',
  components: {
    Conversor
  }
};
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

.line {
  display: flex;
  gap: 60px;
  justify-content: center;
}
</style>
