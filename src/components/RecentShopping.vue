<template>
  <section class="card shopping">
    <header class="shopping__header">
      <div style="display: flex">
        <img class="icon" src="../assets/icons/bag.png" alt="torba na zakupy">
        <h2 class="shopping__heading">Ostatnio dokonane zakupy</h2>
      </div>
      <shopFilter></shopFilter>
    </header>
    <div class="shopping__content">
      <shopTable class="shopping__table" :data="tableData"></shopTable>
    </div>
  </section>
</template>

<script>
import Filter from "./Filter";
import Table from "./Table";

export default {
  name: "shopping",
  components: {
    shopFilter: Filter,
    shopTable: Table
  },
  data() {
    return {
      tableData: [
        {
          client: "Paweł Nowakowski",
          product: "Elegant fence 1800/1950 x 1800mm",
          cost: 6000,
          rabat: 10
        },
        {
          client: "Paweł Nowakowski",
          product: "Elegant fence 1800/1950 x 1800mm",
          cost: 6000,
          rabat: 10
        },
        {
          client: "Paweł Nowakowski",
          product: "Elegant fence 1800/1950 x 1800mm",
          cost: 6000,
          rabat: 10
        },
        {
          client: "Paweł Nowakowski",
          product: "Elegant fence 1800/1950 x 1800mm",
          cost: 6000,
          rabat: 10
        },
        {
          client: "Paweł Nowakowski",
          product: "Elegant fence 1800/1950 x 1800mm",
          cost: 6000,
          rabat: 10
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.shopping {
  max-width: 1100px;
  padding-bottom: 1rem;
}

.shopping__header {
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

  @media screen and (max-width: 678px) {
    display: block;
    height: auto;
  }
}

.shopping__heading {
  display: flex;
  font-size: 26px;
  color: #000000;
  font-weight: bold;

  @media screen and (max-width: 678px) {
    margin-bottom: 1rem;
  }
}

.shopping__content {
  overflow: auto;
}

.shopping__table {
  width: 100%;
}
</style>
