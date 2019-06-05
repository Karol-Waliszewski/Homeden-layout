<template>
  <section class="card stats">
    <header class="stats__header">
      <img class="icon" src="../assets/icons/chart.png" alt="wykres liniowy">
      <h2 class="stats__heading">Statystyki</h2>
    </header>
    <div class="stats__content">
      <h3 class="stats__label">Wykres zrealizowanych sprzedaży do liczby udzielonych rabatów</h3>
      <div class="stats__chart">
        <chart :data="chart.data" :options="chart.options"></chart>
      </div>
      <div class="stats__summary">
        <p class="stats__key">Zrealizowane sprzedaże:</p>
        <span class="stats__value">64%</span>
      </div>
      <div class="stats__summary">
        <p class="stats__key">Udzielonych rabatów:</p>
        <span class="stats__value">36%</span>
      </div>
    </div>
  </section>
</template>

<script>
import PieChart from "./PieChart";

export default {
  name: "stats",
  data() {
    return {
      chart: {
        data: {
          labels: ["Udzielonych rabatów", "Zrealizowane sprzedaże"],
          datasets: [
            {
              label:
                "Wykres zrealizowanych sprzedaży do liczby udzielonych rabatów",
              data: [86, 153]
            }
          ]
        },
        options: {
          legend: false,
          responsive: true
        }
      }
    };
  },
  components: {
    chart: PieChart
  }
};
</script>

<style lang="scss" scoped>
.stats {
  max-width: 400px;
}

.stats__header {
  display: flex;
  align-items: center;
  height: 110px;
  padding: 30px 50px;
  position: relative;
  &:after {
    content: "";
    display: block;
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 1px;
    background: rgba(#000000, 0.05);
  }
}

.stats__heading {
  font-size: 26px;
  color: #000000;
  font-family: "Proxima Nova";
  font-weight: bold;
}

.stats__content {
  padding: 25px 50px;
}

.stats__label {
  font-size: 15px;
  line-height: 21px;
  color: #a1a1a1;
  font-family: "Proxima Nova";
  font-weight: 300;
  margin-bottom: 30px;
}

.stats__chart {
  width: 180px;
  margin-bottom: 25px;
}

.stats__summary {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 200px;
  margin-bottom: 1rem;
}

.stats__key {
  max-width: 50%;
  line-height: 15px;
  color: #a1a1a1;
  font-family: "Proxima Nova";
  font-weight: 300;
}

.stats__value {
  font-size: 36px;
  //line-height: 60px;
  color: #000000;
  font-family: "Proxima Nova";
  font-weight: 300;
}
</style>
