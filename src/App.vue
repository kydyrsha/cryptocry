<template>
<section>
    <div class="ticker">
      <h2>Ticker</h2>
      <input
        v-model="ticker"
        v-on:keydown.enter="add"
        type="text"
        placeholder="DADA">
      <button @click="add">add</button>
    </div>
    <div class="container">
      <div
        v-for="t in tickers"
        :key="t"
        class="card">
        <p>{{ t.name }} - USD</p>
        <h3>{{ t.price }}</h3>
        <button>delete</button>
      </div>
    </div>
</section>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      ticker: "default",
      tickers: [{
        name: 'DEMO1',
        price: '0.01'
      },{
        name: 'DEMO2',
        price: '0.02'
      },{
        name: 'DEMO3',
        price: '0.03'
      }]
    };
  },
  methods: {
    add() {
      const newTicker = {
        name: this.ticker,
        price: '-'
      };
      this.tickers.push(newTicker);
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,400;0,700;1,400&display=swap');

body {
  font-size:100%;
  margin:0;
  box-sizing: border-box;
  color:#000;
  font-family: 'Noto Sans', sans-serif;
}

section {
  width:100%;
  max-width:1200px;
  margin:0 auto;
}

section .ticker {
  display:flex;
  flex-direction: column;
  align-items: flex-start;
}

section .ticker h2 {
  margin: 1rem 0;
}

section .ticker input {
  margin-bottom: 1rem;
}

section .container {
  padding:2rem 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

section .container .card {
  border:2px solid #000000;
  border-radius: 0.5rem;
  width:25%;
  text-align: center;
  padding:1rem;
  margin:1rem;
}

</style>
