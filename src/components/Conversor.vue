<template>
  <div class="conversor">
    <h2>{{ moedaA }} Para {{ moedaB }}</h2>
    <input
      type="text"
      v-model="moedaA_value"
      :placeholder="moedaA"
      @keydown.enter="converter"
    />
    <input
      class="button-converter"
      type="button"
      value="converter"
      @click="converter"
    />
    <h2>{{ moedaB }} {{ moedaB_value }}</h2>
  </div>
</template>

<script>
export default {
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "",
      moedaB_value: 0,
    };
  },
  methods: {
    converter() {
      let de_para = this.moedaA + "_" + this.moedaB;
      let url =
        "https://free.currconv.com/api/v7/convert?q=" +
        de_para +
        "&compact=ultra&apiKey=3272e208457b8965cbe7";
      fetch(url)
        .then((res) => {
          return res.json();
        })
        .then((json) => {
          let cotacao = json[de_para];
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value))
            .toFixed(2)
            .replace(".", ",");
        });
    },
  },
};
</script>

<style>
.conversor {
  padding: 20px;
  max-width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
.button-converter {
  background-color: green;
  color: #fff;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
}
</style>