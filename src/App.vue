<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>

  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue";
export default {
  name: "app",
  components: { Conversor },
};
</script>

<style>
  #app {
    padding: 20px;
    max-width: 900px;
    margin: auto;
    background-color: #85FFBD;
    background-image: linear-gradient(45deg, #85FFBD 0%, #FFFB7D 100%);
    border-radius: 8px;
  }
  .linha{
    display: flex;
    justify-content: space-around;
    margin-top: 30px;
    color: rgb(103, 153, 3);
  }
  h1{
    text-align: center;
    color: green;
  }
</style>