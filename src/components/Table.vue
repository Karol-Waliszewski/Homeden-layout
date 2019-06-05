<template>
  <table class="table" cellspacing="0" cellpadding="0">
    <tr class="table__header">
      <th class="table__heading">Klient</th>
      <th class="table__heading">Produkt</th>
      <th class="table__heading">Kwota</th>
      <th class="table__heading">Wykorzystany rabat</th>
    </tr>
    <tr class="table__row" v-for="(row, index) in data" :key="index">
      <td class="table__data">{{row.client}}</td>
      <td class="table__data">{{row.product}}</td>
      <td class="table__data">{{row.cost}} $</td>
      <td class="table__data">{{row.rabat}} %</td>
    </tr>
  </table>
</template>

<script>
export default {
  name: "shopTable",
  props: ["data"]
};
</script>

<style lang="scss">
.table {
  border: 0;
}

.table__header {
  text-align: left;
  text-transform: uppercase;
  font-size: 13px;
  color: #a1a1a1;
  font-family: "Proxima Nova";
}

.table__heading {
  &:first-child {
    padding-left: 50px;
    padding-top: 25px;
    padding-bottom: 25px;
  }
  &:not(:first-child) {
    padding-top: 25px;
    padding-bottom: 25px;
    padding-right: 50px;
  }
}

.table__row {
  cursor: pointer;
  transition: box-shadow 200ms;

  &:nth-child(2n) {
    background-color: #fafafa;
  }
  &:hover {
    box-shadow: 1.5px 2.598px 16px rgba(0, 0, 1, 0.1);
    .table__data:first-child::before {
      opacity: 1;
    }
  }
}

.table__data {
  font-size: 14px;
  color: #000000;
  font-family: "Proxima Nova";

  &:first-child {
    padding-left: 50px;
    padding-top: 25px;
    padding-bottom: 25px;
    position: relative;
    &::before {
      content: "";
      display: block;
      position: absolute;
      width: 4px;
      height: 28px;
      background-color: #f15922;
      left: 10px;
      top: 50%;
      transform: translateY(-50%);
      opacity: 0;
      transition: opacity 200ms;
    }
  }

  &:not(:first-child) {
    padding-top: 25px;
    padding-bottom: 25px;
    padding-right: 50px;
  }
}
</style>
