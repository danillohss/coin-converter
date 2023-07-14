<template>
  <div class="converter">
    <h2>{{ coinA }} > {{ coinB }}</h2>
    <input v-model="coinA_value" type="text" :placeholder="coinA" />
    <button @click="converter">Converter</button>
  </div>
</template>

<script>
export default {
  name: "CONVERTER",
  props: ["coinA", "coinB"],
  data() {
    return {
      coinA_value: "",
      coinB_value: "",
    };
  },
  methods: {
    converter() {
      let url = `http://free.currencyconverterapi.com/api/v5/convert?q=${this.coinA}_${this.coinB}&compact=y`;
      fetch(url);
    },
  },
};
</script>