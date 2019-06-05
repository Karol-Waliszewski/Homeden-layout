<template>
  <table class="table" cellspacing="0" cellpadding="0">
    <tr>
      <th>Klient</th>
      <th>Produkt</th>
      <th>Kwota</th>
      <th>Wykorzystany rabat</th>
    </tr>
    <tr v-for="(row, index) in data" :key="index">
      <td>{{row.client}}</td>
      <td>{{row.product}}</td>
      <td>{{row.cost}} $</td>
      <td>{{row.rabat}} %</td>
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
  tr {
    cursor: pointer;
    transition: box-shadow 200ms;

    &:nth-child(2n) {
      background-color: #fafafa;
    }
    &:not(:first-child):hover {
      box-shadow: 1.5px 2.598px 16px rgba(0, 0, 1, 0.1);
      td:first-child::before {
        opacity: 1;
      }
    }
  }
  th {
    text-align: left;
    text-transform: uppercase;
    font-size: 13px;
    color: #a1a1a1;
    font-family: "Proxima Nova";
  }
  td {
    font-size: 14px;
    color: #000000;
    font-family: "Proxima Nova";
  }
  td:first-child,
  th:first-child {
    padding-left: 50px;
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
  td:not(:first-child),
  th:not(:first-child) {
    padding-top: 25px;
    padding-bottom: 25px;
    padding-right: 50px;
  }
}
</style>
